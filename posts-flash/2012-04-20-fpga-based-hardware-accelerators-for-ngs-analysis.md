---
title: FPGA-based Hardware Accelerators for NGS Analysis
tags:
- FPGA
categories:
- blog
---
Advances in next-generation sequencing generates so much data that researchers
are looking into all types of technological solutions for rapid analysis. So
far we mostly covered software-based algorithmic approaches. However, a scale
up in speed of several orders of magnitude can be achieved by designing custom
hardware for specific tasks.
<!--more-->

What is a hardware-based approach? In our day-to-day life as
bioinformaticians, we mostly deal with computers as black boxes. We send
commands to that black box using a keyboard and the computer returns us
answers through the monitor. Rarely do we open up the box to see what it
inside or try to tweak its performance. In fact, for work on cloud computers,
we do not even know where the box resides.

In a hardware-based approach, the things inside the box are redesigned to
solve problems in bioinformatics. More specifically, a special card is
designed for BLAST search, short read search or other problem. Conceptually,
it is similar to the wireless card or ethernet card that we plug into the
computers as add ons. The process involves -

(i) opening the box to plug the card in,

(ii) add a software driver to the operating system,

(iii) writing computer codes to use the card.

Designing the card itself is the real challenge. There are two options -

(i) using FPGAs, which are reprogrammable computer chips. These chips can be
programmed for various tasks. FPGAs are inexpensive and can give 10 to 100x
increase in speed compared to software solutions.

(ii) designing custom chips for the tasks and manufacturing them. Custom chips
can give another 100x increase in speed compared to FPGAs, but their
manufacturing is expensive.

We tend to focus too much on speed, but hardware-based solutions are very
useful for another reason. They can solve the problems using only a fraction
of power compared to software-based solution using a large server. The other
day, we were going through the specs of a Dell server and one of us commented
- 'hey, this computer will use same amount power as my entire house, even when
it is idle'. Cost of electricity is a big concern for companies with too many
servers, so much so that they even end up buying huge [wind
farms](http://en.wikipedia.org/wiki/Google_Energy). So, using low energy is as
important a metric for choice of technology as the increase in speed.

FPGA-based solutions are being tried by various groups. Following two reports
are helpful, if you want to further explore this topic.

[Short-Read DNA Sequence Alignment with Custom Designed FPGA-based Hardware](h
ttps://circle.ubc.ca/bitstream/handle/2429/30008/ubc_2011_spring_hall_adam.pdf
?sequence=1)

[Hardware Acceleration of Short Read Mapping](http://www.ee.washington.edu/fac
ulty/hauck/publications/FCCMshortread.pdf)

