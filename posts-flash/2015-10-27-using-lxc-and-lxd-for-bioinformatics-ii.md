---
title: Using LXC and LXD for Bioinformatics - (ii)
tags: []
categories:
- blog
---
**Virtualization**
<!--more-->

We have been researching alternative virtualization/containerization stacks to
be installed on the servers. The first model we considered was Docker (on top
of CoreOS) and thought that was wonderful. CoreOS promised to run a minimal
operating system, and then every program could be sheltered within a Docker
container. Moreover, Docker/CoreOS promised to get 'bare metal' performance.

However, after careful consideration, we decided to reject the model for
security reasons. Our current plan is to use virtualization and then one of
the virtualized OSs can be used for container experiments. Moreover, the
container technology will be anything but Docker, because we want them to run
on unprivileged mode.

For virtualization, there are three alternatives - ESXi (owned by VMWare-->
EMC --> Dell), Xen and KVM. After going through all discussions on the Type 1
vs Type 2 hypervisors, we realized that they are mostly too simplistic models
of currently available programs. For example, KVM is a 'type 2' hypervisor
(i.e. needs a native operating system to run instead of 'bare metal'), but it
actually performs as good as native operating system. Anyway, here are more
details on the three choices.

**ESXi** \- closed source and became too expensive after EMC's purchase of VMWare. 

**Xen** \- open-source and appears very impressive. 

**KVM** \- open-source and supposedly less feature-rich than Xen, because Xen has been in development for over a decade. 

Initially we were going for Xen. However, [a benchmark on
MAFFT](https://major.io/2014/06/22/performance-benchmarks-kvm-vs-xen/) made us
choose KVM. Not that the differences are anywhere beyond third digit, but at
least it shows that KVM does not degrade performance.

\---------------------------------------------

**Guest operating systems**

We are currently planning to choose [Arch Linux](https://www.archlinux.org/).

> **A simple, lightweight distribution**

You've reached the website for Arch Linux, a lightweight and flexible Linux
distribution that tries to Keep It Simple.

Currently we have official packages optimized for the i686 and x86-64
architectures. We complement our official package sets with a community-
operated package repository that grows in size and quality each and every day.

Our strong community is diverse and helpful, and we pride ourselves on the
range of skillsets and uses for Arch that stem from it. Please check out our
forums and mailing lists to get your feet wet. Also glance through our wiki if
you want to learn more about Arch.

\---------------------------------------------

**Containerization - LXC/LXD**

LXD is in early development. So, mostly we will be working with LXC. A good
introduction is [here](https://linuxcontainers.org/lxc/introduction/). We plan
to install four guest O/Ss and one of them will be used for experimentation
with LXC.

\---------------------------------------------

**Web stack - NGINX, GO framework, Postgres, some kind of CMS**

We will discuss this topic, when we reach there.

