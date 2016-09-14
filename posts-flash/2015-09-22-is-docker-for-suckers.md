---
title: Is Docker for Suckers?
tags: []
categories:
- blog
---
Recently we have been noticing an unusual surge in interest about Docker
within the bioinformatics community. Here is a little review for their
benefit.
<!--more-->

![hqdefault](http://www.homolog.us/blogs/wp-content/uploads/2015/09/hqdefault-
300x225.jpg)

**What is Docker?**

**Docker helps you keep your server secure** by encapsulating each programs so that a bad program does not bring down the entire server or a malicious program cannot take over the entire server. You can conceptually think about each unix process running in its controlled environment through Docker. You specify its own territory (RAM, disk, network port, etc.) before-hand and the program has to live within that territory. 

**Wow, isn't that innovative?**

Yes, it is, but the real innovation came [the kernel developers of the Linux
operating system](https://en.wikipedia.org/wiki/Cgroups).

> cgroups (abbreviated from control groups) is a Linux kernel feature that
limits, accounts for, and isolates the resource usage (CPU, memory, disk I/O,
network, etc.) of a collection of processes.

Engineers at Google (primarily Paul Menage and Rohit Seth) started the work on
this feature in 2006, under the name "process containers".[1] In late 2007 the
nomenclature changed to "control groups" due to the confusion caused by
multiple meanings of the term "container" in the Linux kernel context, and
control-group functionality merged into kernel version 2.6.24.[2] Since then,
developers have added many new features and controllers, such as support for
kernfs,[3] firewalling,[4] and unified hierarchy.[5]

One of the design goals of cgroups is to provide a unified interface to many
different use cases, from controlling single processes (by using nice, for
example) to whole operating system-level virtualization (as provided by
OpenVZ, Linux-VServer or LXC, for example). Cgroups provides:

Resource limitation: groups can be set to not exceed a configured memory
limit, which also includes the file system cache[6][7]

Prioritization: some groups may get a larger share of CPU utilization[8] or
disk I/O throughput[9]

Accounting: measures how much resources certain systems use, which may be
used, for example, for billing purposes[10]

Control: freezing the groups of processes, their checkpointing and
restarting[10]

**But who would write code at the kernel level? Docker makes that easy, no?**

Well, there is another free and open-source program provided by the developers
of linux ([LXC](https://en.wikipedia.org/wiki/LXC)) to do the job for you.

> LXC (Linux Containers) is an operating-system-level virtualization
environment for running multiple isolated Linux systems (containers) on a
single Linux control host.

The Linux kernel provides the cgroups functionality that allows limitation and
prioritization of resources (CPU, memory, block I/O, network, etc.) without
the need for starting any virtual machines, and namespace isolation
functionality that allows complete isolation of an applications' view of the
operating environment, including process trees, networking, user IDs and
mounted file systems.[3]

LXC even has a user-friendly GUI to monitor processes. It cannot be any
easier.

![lxc5-1024x469](http://www.homolog.us/blogs/wp-
content/uploads/2015/09/lxc5-1024x469-300x137.png)

**Who would be the best Docker users?**

Docker and bioinformatics are match made in heaven. The current culture in
bioinformatics is to run program as packages without understanding what is
inside, and Docker takes not knowing what one does to an art form !! Let us
explain that by reviewing various aspects of Docker and its 'ecosystem'.

**a) Dockerhub**

Just like Github, Docker created Dockerhub to swap in and out packages. The
difference with github is that you may be exchanging untrusted binaries.
**Remember, you invited Docker to your house in the first place to keep your
place secure.**

**b) Libcontainer vs LXC**

Docker started with relying on Linux LXC, which has gone through various
rounds of review and updates to be secure. For example -

> Originally, LXC containers were not as secure as other OS-level
virtualization methods such as OpenVZ: in Linux kernels before 3.8, the root
user of the guest system could run arbitrary code on the host system with root
privileges, much like chroot jails.[4] Starting with the LXC 1.0 release, it
is possible to run containers as regular users on the host using "unprivileged
containers".[5] Unprivileged containers are more limited in that they cannot
access hardware directly. Nevertheless, even privileged containers should
provide adequate isolation in the LXC 1.0 security model, if properly
configured.[5]

Then somewhere along the way, it made its own libcontainer as the default
container library. **Remember, you invited Docker to your house in the first
place to keep your place secure.**

**c) Docker on bare metal**

Now that Docker does everything, a number of new ideas are being proposed
about getting rid of much of operating system.

CoreOS and RancherOS are two such minimal operating systems.

If you are familiar with unix operating system, you know that 'init' is the
first process (PID=1) and it starts a number of other processes. There is
already a massive controversy in the linux community about systemd taking the
place of init. According to linux veterans, systemd boots up the computer fast
at the cost of security.

> Between October 2013 and February 2014, a long debate among the Debian
Technical Committee occurred on the Debian mailing list,[72] discussing which
init system to use as the default in Debian 8 "jessie", and culminating in a
decision in favor of systemd. The debate was widely publicized[73][74] and in
the wake of the decision the debate continues on the Debian mailing list.

...

In March 2014, Eric S. Raymond opined that systemd's design goals were prone
to mission creep and software bloat.[78] In April 2014, Linus Torvalds
expressed reservations about the attitude of Kay Sievers, a key systemd
developer, toward users and bug reports.[79]

In late April 2014, a campaign to boycott systemd was launched, with a website
listing various reasons against its adoption.[80][81]

In an August 2014 article published in InfoWorld, Paul Venezia wrote about the
systemd controversy, and attributed the controversy to violation of the Unix
philosophy, and to "enormous egos who firmly believe they can do no
wrong".[82] The article also characterizes the architecture of systemd as
similar to that of svchost.exe, a critical system component in Microsoft
Windows with a broad functional scope.[82]

In November 2014, Debian maintainers and Technical Committee members Joey
Hess,[83] Russ Allbery,[84] Ian Jackson[85] and systemd package maintainer
Tollef Fog Heen[86] resigned from their positions. All three justified their
decision on the public Debian mailing list and in personal blogs with their
exposure to extraordinary stress levels related to ongoing disputes on systemd
integration within the Debian and open source community that rendered regular
maintenance virtually impossible.

In December 2014, a fork of Debian, called Devuan, was announced by a group
calling themselves the "Veteran Unix Admins". Its intention is to provide a
Debian variant without systemd installed by default.[87]

Docker muddies the water even more, because it must also run as root or have
the same privileges as systemd. CoreOs allows that by closely integrating
Docker with its minimal operating system, whereas RancherOS goes a step
further by giving Docker PID=1 !!

**Remember, you invited Docker to your house in the first place to keep your place secure.**

**d) Lightweight?**

It is true that Docker is lightweight compared to running a full virtual
machine, but that should not be the basis of comparison. The real comparison
should be LXC, and it appears that [Docker limits the abilities of users
compared to what LXC already provides](https://www.flockport.com/lxc-vs-
docker/).

> Docker restricts the container to a single process only. The default docker
baseimage OS template is not designed to support multiple applications,
processes or services like init, cron, syslog, ssh etc.

As we saw earlier this introduces a certain amount of complexity for day to
day usage scenarios. Since current architectures, applications and services
are designed to operate in normal multi process OS environments you would need
to find a Docker way to do things or use tools that support Docker.

Take a simple application like WordPress. You would need to build 3 containers
that consume services from each other. A PHP container, an Nginx container and
a MySQL container plus 2 separate containers for persistent data for the Mysql
DB and WordPress files. Then configure the WordPress files to be available to
both the PHP-FPM and Nginx containers with the right permissions, and to make
things more exciting figure out a way to make these talk to each other over
the local network, without proper control of networking with randomly assigned
IPs by the Docker daemon! And we have not yet figured cron and email that
WordPress needs for account management. Phew!

This is a can of worms and a recipe for brittleness. This is a lot of work
that you would just not have to even think about with OS containers. This adds
an unbelievable amount of complexity and fragility to basic deployment and now
with hacks, workarounds and entire layers being developed to manage this
complexity. This cannot be the most efficient way to use containers.

Can you build all 3 in one container? You can, but then why not just simply
use LXC which is designed for multi processes and is simpler to use. To run
multiple processes in Docker you need a shell script or a separate process
manager like runit or supervisor. But this is considered an 'anti-pattern' by
the Docker ecosystem and the whole architecture of Docker is built around
single process containers.

If you are not satisfied, please take a look these excellent posts discussing
Docker -

[Lets review.. Docker (again)](http://iops.io/blog/docker-hype/)

[The case against Docker](https://www.andreas-jung.com/contents/the-case-
against-docker)

[Understanding the key differences between LXC and
Docker](https://www.flockport.com/lxc-vs-docker/)

[boycott docker](http://www.boycottdocker.org/)

[Reddit: Docker is fundamentally flawed, useless hype (iops.io)](https://www.r
eddit.com/r/sysadmin/comments/2v4fqe/docker_is_fundamentally_flawed_useless_hy
pe)

[Reddit: Many reasons why you should stop using Docker (iops.io)](https://www.
reddit.com/r/programming/comments/2vmaxc/many_reasons_why_you_should_stop_usin
g_docker/)

