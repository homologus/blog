---
title: Hadoop at JGI (NERSC)?
tags: []
categories:
- blog
---
For new readers, easiest way to follow us is through our [twitter
feed](https://twitter.com/#!/homolog_us/). The feed is updated, whenever we
post a commentary here.
<!--more-->

When we investigated various technologies to achieve scaling over large NGS
data sets, Hadoop came out on top for two reasons - (i) scaling using
inexpensive hard disks is cheaper than scaling using expensive RAM, (ii)
Hadoop technology comes for free due to its adoption by large internet
community. Our Hadoop-related discussions are available
[here](http://www.homolog.us/blogs/category/hadoop/).

It was heartening to find out that big genome centers are starting to see the
merits of the technology. A collaborator forwarded me [this
ad](http://www.bioinformatics.org/forums/forum.php?forum_id=9343) \-

> The individual is expected to provide assistance on how to architect and
implement genomic applications that would include porting or modifying
existing pipelines to run on new architectures and platforms including HPC
systems and Cloud computing systems. This includes investigating and
developing new more efficient and scalable algorithms that can handle the
growing volume of genomic data. In addition, the **individual will have the
opportunity to explore new computing models such as Hadoop, HBase, and
accelerators to understand how they can be used to address challenges for the
JGI**.

(emphasis mine).

and later in the ad -

> * An advanced degree in computational science, computer science, or
bioinformatics

* Familiarity with high-performance computing (including MPI , novel architectures (accelerator, FPGA, etc) or cloud computing 

* Familiarity with emerging distributed computing models such as Hadoop 

* Experience supporting and deploying bioinformatics pipelines 

Please note that we are not getting paid by JGI to promote the above ad,
neither are we planning to open a Champagne bottle every time someone utters
Hadoop. Our interest in mentioning the ad is completely different. We like to
point out a technology that had been completely missed by our previous
discussions, but is mentioned above. It is [FPGA](http://en.wikipedia.org/wiki
/Field-programmable_gate_array) (field-programmable gated array).

When we were based in Silicon valley, we explored the FPGA idea for high-
throughput analysis of bioinformatic data. We started discussing with a
company located in Los Gatos, CA developing BLAST hardware accelerators using
FPGA, but their prices seemed too high and we did not follow up. I cannot
locate the company at this moment, but found another company called [TimeLogic
building similar hardware](http://www.timelogic.com/). Also, we found an open
source project called [Mitrion-C](http://mitc-openbio.sourceforge.net/)
dedicated to the same purpose.

Here is a quick explanation of FPGA technology. A computer can solve a problem
in two ways -

(i) **software solution** \- the chips give you small number of hardware-
implemented 'operations', and you use those operations in a software code to
do your task,

(ii) **hardware solution** \- you build a new chip to solve the problem.

For a simple example, let us say your computer has one chip that can only add
numbers. However, you can write code to use the adder many times to multiply
numbers. That is a software solution. On the other hand, you can build a [new
multiplication chip](http://ieeexplore.ieee.org/Xplore/login.jsp?url=http%3A%2
F%2Fieeexplore.ieee.org%2Fiel5%2F12%2F35248%2F01676634.pdf%3Farnumber%3D167663
4&authDecision=-203). (Incidentally, designing efficient multiplication
algorithms for VLSI chips was seemed like the most difficult problem in our
undergraduate class of digital circuits 101, until we got involved into making
the whole enchilada - an entire microprocessor - in the next class).

The above example shows the relative merits and demerits of two approaches.
Software approach is easy to implement, but runs slow. Hardware approach can
be very fast, but is difficult and expensive to build. The biggest expense of
using custom chips comes from creating hardware masks for photo-lithography of
the transistor gates and their interconnections, because what the software
approach did through coding is essentially replicated by connecting transistor
gates in the hardware approach.

FPGA is a happy marriage of the two approaches. In this case, FPGA vendors
like Xilinx and Altera sell generic chips with many interconnected or partly
interconnected gates with fuses in between them. Then the user reprograms that
generic chip to build custom chip for his own specific use (say BLAST or
Bowtie). This reprogramming essentially boils down to blowing off fuses here
and there on the chip. That is far less expensive than creating a custom chip
from scratch.

Why did not anyone try this approach earlier with biological programs? It is
because the FPGA chips were not that complex earlier. The density of
transistors within a chip area doubles every 1.5 year or so according to
[Moore's law](http://en.wikipedia.org/wiki/Moore's_law). That means the FPGA
chips of 2011 can do lot more than FPGAs of 2007, which themselves were far
better than FPGAs of 2003.

We will add a more detailed commentary on this topic later.

