---
title: What is the True Computing Cost of RNAseq Analysis? - Titus Brown&#039;s Slides
tags: []
categories:
- rnaseq
---
Titus Brown posted nice set of slides with complete protocols for RNAseq and
Metagenome analysis (see below), but let us get to the part that we find the
most valuable. He made **honest estimate** of time and cost for bioinformatic
analysis and came to the numbers shown in the following figure. We confirmed
with him that the estimate of $150 is meant to be for per sample, and not the
entire experiment.
<!--more-->

![Capture](http://www.homolog.us/blogs/wp-
content/uploads/2014/01/Capture2-300x217.png)

Why do we stress on **honest estimate**? Biologists have good understanding of
experimental cost, which is usually given by adding the prices of
kits/reagents, lab-space (comes as overhead), personnel and depreciated large
equipments. An wide range of experimental service providers benchmarked those
costs and offer 'standard prices' for sequencing/lane. Any service provider,
who significantly underestimates the cost, usually either provides low quality
service or goes out of business.

The cost of computing, on the other hand, is often grossly under-estimated,
because many small and infrequent tasks are often assumed to be cost-free.

(i) **Backup**: Backup, and especially truly fault-tolerant backup of critical
data, gets the least priority behind other supposedly important tasks until
the hard-drive crashes. Proper backup needs planning, and that adds to the
cost.

(ii) **Software upgrade**: Open-source software programs keep changing every
day. If someone does not do periodic upgrades of relevant libraries, sooner or
later, they stop talking to each other. In an academic lab, that someone is
often a 'cost-free' graduate student.

(iii) **Hardware upgrade**: Hardware upgrades cost upfront money, and then
that expense supposedly gets recovered through better performance of code. If
hardware is not upgraded, programs run slowly. However, slow execution of
program can be perceived by someone as cost-free. After all, if you own your
server, what is the extra cost of running the analysis in 1.5 days instead of
1 day? After all, the machine is going to sit idle otherwise.

(iv) **Power**: When a researcher keeps a cluster of large servers, energy
costs start to add up. However, in an academic organization, the cost of
keeping the lights on and machines up goes to a different account.

(v) **Machine Hang/Crash**: The server crashes or hangs every once in a while.
That hapless 'cost-free' graduate student is expected to reset it.

(vi) **Depreciation**: Computers depreciate, and depreciate very fast. Among
researchers, this is possibly the only well-understood component.

What happens, if computing costs are underestimated? The poor graduate student
stays stuck in the lab for ever, and blames himself for not being able to do
any research.

We like the approach of Titus for benchmarking the true cost of bioinformatic
analysis, where he makes his estimates on Amazon cloud. In case of Amazon or
other cloud service providers, (i-vi) happen quite frequently or is big enough
component of business, and therefore they have to keep real personnel at the
job. So, the cost/hour of Amazon cloud properly reflects the cost of computing
experiment. Therefore, the message of his estimate should not be 'Amazon cloud
is too damn expensive' and our HPC guys are much better. It should rather be -
'Oh gosh, I did not realize the hidden costs of analyzing of 40 RNAseq
libraries'.

We thank him for completing the benchmarking, because it is very time-
consuming engineering task. There are simply too many variables and sometimes
it is unclear, whether moving from a small Amazon box to big Amazon box will
increase the overall costs or decrease it. We tried to do it for our RNAseq
analysis pipeline, but gave up after a few steps by being distracted. [Based
on his related blog posts on benchmarking of k-mer counting in
EC2](http://ivory.idyll.org/blog/kmer-counting-benchmarks.html), we know that
Titus has been done quite thorough work and therefore his estimates are

His full slides are below:

** [2014 khmer protocols](https://www.slideshare.net/c.titus.brown/2014-khmer-protocols) ** from **[c.titus.brown](http://www.slideshare.net/c.titus.brown)**

He also referred to his upcoming [Pycon
talks](https://us.pycon.org/2014/schedule/presentation/181/) that should be
very informative. We are not allowed to follow him on twitter (by his choice),
but hopefully someone will forward a video that we will present to our
readers.

>

Description

Cloud computing offers some great opportunities for science, but most cloud
computing platforms are I/O and memory limited, and hence are poor matches for
data-intensive computing. After 4 years of research software development we
are now instrumenting and benchmarking our analysis pipelines; numbers,
lessons learned, and future plans will be discussed. Everything is open
source.

Abstract

The cloud provides great opportunities for a variety of important
computational science challenges, including reproducible science, standardized
computational workflows, comparative benchmarking, and focused optimization.
It can also help be a disruptive force for the betterment of science by
eliminating the need for large infrastructure investments and supporting
exploratory computational science on previously challenging scales. However,
most cloud computing use in science so far has focused on relatively mundane
"pleasantly parallel" problems. Our lab has spent many moons addressing a
large, non-parallelizable "big data/big graph" problem -- sequence assembly --
with a mixture of Python and C++, some fun new data structures and algorithms,
and a lot of cloud computing. Most recently we have been working on open
computational "protocols", worfklows, and pipelines for democritizing certain
kinds of sequence analysis. As part of this work we are tackling issues of
standardized test data sets to support comparative benchmarking, targeted
optimization, reproducible science, and computational standardization in
biology. In this talk I'll discuss our efforts to understand where our
computational bottlenecks are, what kinds of optimization and parallelization
efforts make sense financially, and how the cloud is enabling us to be
usefully disruptive. As a bonus I'll talk about how the focus on pleasantly
paralellizable tasks has warped everyone's brains and convinced them that
engineering, not research, is really interesting.

