---
title: Using LXC and LXD for bioinformatics
tags: []
categories:
- blog
---
Over the next 2-3 weeks, I will be configuring a server with LXC/LXD (on top
of Xen or KVM) to use it for bioinformatics. If you have similar interests,
please let me know and we can share notes through our chat-based communication
system (self-hosted Slack-like software).
<!--more-->

The reason I am doing this is to avoid Docker at all costs. Although Docker
provides some advantages in installation of programs, they are far out-weighed
by the disadvantages (See [Is Docker for
Suckers?](http://www.homolog.us/blogs/blog/2015/09/22/is-docker-for-
suckers/)). However, containers themselves have a number of benefits and the
best way to get them is to use unprivileged containers from LXC. Docker does
not provide unprivileged containers, and the system becomes insecure as a
result.

If the LXC/LXD experiment is successful, I will later put together a blog post
to describe the process.

