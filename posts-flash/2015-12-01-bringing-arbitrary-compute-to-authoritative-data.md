---
title: Bringing Arbitrary Compute to Authoritative Data
tags: []
categories:
- blog
---
Computation on large data sets often require copying files from 'storage' to
the 'computing node'. That leads to creation of second copy of original data
file, which itself is large, and the process is inefficient. There could be
another model, where 'compute' is brought to data stored only once. In this
context, readers may enjoy the following two papers -
<!--more-->

[There's Just No Getting around It: You're Building a Distributed
System](http://queue.acm.org/detail.cfm?id=2482856)

>

**Building a distributed system requires a methodical approach to requirements.**

Distributed systems are difficult to understand, design, build, and operate.
They introduce exponentially more variables into a design than a single
machine does, making the root cause of an application problem much harder to
discover. It should be said that if an application does not have meaningful
SLAs (service-level agreements) and can tolerate extended downtime and/or
performance degradation, then the barrier to entry is greatly reduced. Most
modern applications, however, have an expectation of resiliency from their
users, and SLAs are typically measured by "the number of nines" (e.g., 99.9 or
99.99 percent availability per month). Each additional 9 becomes harder and
harder to achieve.

To complicate matters further, it is extremely common that distributed
failures will manifest as intermittent errors or decreased performance
(commonly known as brownouts). These failure modes are much more time-
consuming to diagnose than a complete failure. For example, Joyent operates
several distributed systems as part of its cloud-computing infrastructure. In
one such systema highly available, distributed key/value storeJoyent recently
experienced transient application timeouts. For most users the system operated
normally and responded within the bounds of its latency SLA. However, 5-10
percent of requests exceeded a predefined application timeout. The failures
were not reproducible in development or test environments, and they would
often "go away" for minutes to hours at a time. Troubleshooting this problem
to root cause required extensive system analysis of the data-storage API
(node.js), an RDBMS (relational database management system) used internally by
the system (PostgreSQL), the operating system, and the end-user application
that relied on the key/value system. Ultimately, the root problem was in
application semantics that caused excessive locking, but determining the root
cause required considerable data gathering and correlation, and consumed many
working hours of time among engineers with differing areas of expertise.

The entire preamble is fairly common knowledge to engineers working on
distributed systems, and the example application degradation is typical of a
problem that arises when operating a large system. Current computing trends,
however, are bringing many more organizations and applications into the
distributed-computing realm than was the case only a few years ago. There are
many reasons why an organization would need to build a distributed system, but
here are two examples:

The demands of a consumer Web site/API or multitenant enterprise application
simply exceed the computing capacity of any one machine.

An enterprise moves an existing application, such as a three-tier system, onto
a cloud service provider in order to save on hardware/data-center costs.

The first example is typical of almost any Internet-facing company today. This
has been well discussed for many years and is certainly a hotbed for
distributed-systems research and innovation, and yet it is not a solved
problem. Any application going live still needs to assess its own requirements
and desired SLAs, and design accordingly to suit its system; there is no
blueprint. The usage patterns of any successful new applications will likely
be different from those that came before, requiring, at best, correct
application of known scaling techniques and, at worst, completely new
solutions to their needs.

The second example is increasingly common, given current trends of moving
existing business applications into the cloud to save on data-center costs,
development time, etc. In many cases, these applications have been running on
single-purpose systems in isolated or low-utilization environments. Simply
dropping them into an environment that is often saturated induces failure more
often than they have ever seen or were designed for. In these cases, the dirty
secret is that applications must be rewritten when moving to cloud
environments; to design around the environment in which an application will be
running requires that it be built as a distributed system.

These two examples are at opposite extremes in terms of the reasons why they
require a distributed solution, yet they both force system designers to
address the same problems. Making matters worse, most real-world distributed
systems that are successful are built largely by practitioners who have gone
through extensive academic tutelage or simply "come up hard," as it were.
While much of the discussion, literature, and presentations focus on vogue
technologies such as Paxos,3 Dynamo,5 or MapReduce4all of which indeed merit
such focusthe reality of building a large distributed system is that many
"traditional" problems are left unsolved by off-the-shelf solutions, whether
commercial or open source.

Continue reading [here](http://queue.acm.org/detail.cfm?id=2482856).

[Bringing Arbitrary Compute to Authoritative
Data](https://queue.acm.org/detail.cfm?id=2645649)

> While the term big data is vague enough to have lost much of its meaning,
today's storage systems are growing more quickly and managing more data than
ever before. Consumer devices generate large numbers of photos, videos, and
other large digital assets. Machines are rapidly catching up to humans in data
generation through extensive recording of system logs and metrics, as well as
applications such as video capture and genome sequencing. Large data sets are
now commonplace, and people increasingly want to run sophisticated analyses on
the data. In this article, big data refers to a corpus of data large enough to
benefit significantly from parallel computation across a fleet of systems,
where the efficient orchestration of the computation is itself a considerable
challenge.

The first problem with operating on big data is maintaining the infrastructure
to store it durably and ensure its availability for computation, which may
range from analytic query access to direct access over HTTP. While there is no
universal solution to the storage problem, managing a storage system of record
(that is, one hosting the primary copy of data that must never be lost)
typically falls to enterprise storage solutions such as SANs (storage area
networks). These solutions do not typically offer WAN (wide area network)
access, however, and they often require extra infrastructure to ingest data
from and export data to arbitrary clients; this is hard to scale with the data
footprint.

Once a system of record is established, computation on large data sets often
requires an ETL (extract-transform-load) step into a system that can actually
perform the computation. Even when the original data format suffices, NAS
(network-attached storage)- and SAN-based systems do not support in-place
computation, instead necessitating an expensive copy over the
networkessentially a nonstarter for petabyte-size data sets.

Finally, there's an important distinction between special-purpose and general-
purpose compute interfaces, meaning the abstraction differences between a SQL-
like interface and a Unix shell. While the former is powerful and the
appropriate choice for many kinds of analyses, it is not appropriate for many
ad-hoc tasks such as video transcoding, compression, or other actions that
work on unstructured or semi-structured data. Existing systems for distributed
computation typically require users to understand a complex framework
(abandoning tools they are familiar with) or use a special-purpose interface
(which often raises the aforementioned data-copy problem each time a new
interface is desired).

The goal of this article is to describe a general-purpose, distributed storage
system that supports arbitrary computation on data at rest. It begins by
detailing the constraints, which direct much of the design; then describes an
implementation called Manta, which can be thought of as a reference
implementation but is certainly not the only way such a system could be
constructed; and ends with the ways in which several common big-data problems
can be solved using Manta.

Constraints

The design constraints can be broadly divided into storage abstraction (how
users store and fetch data), the programming model (how users express in-situ
computation on the data), and how the system provides durable local storage
(how the system durably stores bits on disk).

Storage Abstraction: An Object Store

Building a system to scale means ensuring that capacity can be increased by
adding more hardware. Scaling without downtime and without increasing the
impact of individual component failure requires scaling horizontally, but
Posix file-system and block-storage semantics are very difficult to scale
horizontally. Updates may be very small (a byte within a file system; a block
of a few kilobytes within a block device) and frequent. Even without
considering multiple clients, the tradeoff between operation latency and
durability is difficult: the more data the client is allowed to buffer before
transmitting to the server, the faster operations may execute but the more
data is at risk in the face of a crash. With multiple clients operating on the
same file, a similar tradeoff exists between operation latency and
consistency.

Object storage provides a more constrained model that's simpler to scale. An
object store resembles a file system in that it has a global namespace with
objects (data blobs) and directories (hierarchical collections), but object
stores do not support partial updates. Users can create new objects and delete
old ones, but they cannot update the contents of an existing object without
replacing it entirely. For strong consistency, an object-store implementation
need ensure only that the namespace is transactional; objects themselves are
immutable, and thus easily replicated and cached.

Continue reading [here](https://queue.acm.org/detail.cfm?id=2645649).

