---
title: Major Security Hole Discovered in Popular Library glibc
tags: []
categories:
- blog
---
[Link](http://www.bbc.com/news/technology-35592916)
<!--more-->

> A major computer security vulnerability has been discovered - with experts
cautiously warning it could potentially affect hundreds of thousands of
devices, apps and services.

However, due to the nature of the bug, it is extremely difficult to know how
serious the problem is.

"Many people are running around right now trying to work out if this is truly
catastrophic or whether we have dodged a bullet," said Prof Alan Woodward, a
security expect from the University of Surrey.

Google engineers, working with security engineers at Red Hat, have released a
patch to fix the problem.

It is now up to manufacturers, and the community behind the Linux operating
system, to issue the patch to affected software and devices as soon as
possible.

In a blog post explaining the discovery, Google's team detailed how a flaw in
some commonly-used code could be exploited in a way that allows remote access
to a devices - be it a computer, internet router, or other connected piece of
equipment.

The code can also be within many of the so-called "building blocks" of the web
- programming languages such as PHP and Python are affected, as well as
systems used when logging in to sites or accessing email.

"It's not a sky-is-falling scenario," said Washington D.C-based security
researcher Kenneth White.

"But it's true there's a very real prospect that a sizable portion of
internet-facing services are at risk for hackers to crash, or worse, run
remote code to attack others."

He said that while there is no publicly known attack code using the flaw, it's
a "near certainty" hackers would try to exploit the weakness.

Remote execution

The bug is found in glibc - a open-source library of code that is widely used
in internet-connected devices.

One particular function is domain look-up. This is when the device converts a
typical web domain, say bbc.com, and finds its corresponding IP address so it
can access whatever website or service is needed.

The domain look-up code in glibc contains a bug that could allow hackers to
maliciously implant code within a device's memory. From here, attacks such as
remote execution - controlling the device over the internet - could take
place.

However, Google said it is very hard to exploit the flaw although their
engineers have worked out how. For obvious security reasons they are not
making that public.

The scale of the problem is difficult to determine because it is unclear how
many devices and systems make use of the glibc code.

