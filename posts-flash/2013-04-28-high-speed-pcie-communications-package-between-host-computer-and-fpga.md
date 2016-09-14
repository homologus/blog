---
title: High Speed PCIe Communications Package Between Host Computer and FPGA
tags: []
categories:
- blog
---
> **The Problem**
<!--more-->

You've created an amazing FPGA circuit, and downloaded it to your demo board.
Now you want to monitor and control the circuit from your PC, send data from
the PC to the FPGA and get the results back. If you are using an
Altera/Terasic DE-4 demo board, this package is for you.

Solution: Maybe [this package](http://www.eecg.toronto.edu/~tm4/tme/) until we
find something better.

From the link -

> We are seeing data transfer rates of 16 to 19 Mbytes/second when reading
data from the FPGA, and 50 to 55 Mbytes/second when writing data to the FPGA
from the host.

That means sending 100 million 100 nucleotide reads will take 25 seconds. Are
we doing the math right?

Other useful links -

1\. [PCIe](http://forums.xilinx.com/t5/PCI-Express/PC-communication-with-FPGA-
through-PCI-Express/td-p/127052)

2\. [PCI express from a Xilinx/Altera FPGA to a Linux machine: Making it
easy](http://billauer.co.il/blog/2011/04/pcie-pci-express-tlp-xilinx-fpga-
linux-pc-embedded-x86-arm-spartan/)

3\. [communication from an FPGA to a computer through
PCIE](http://www.alteraforum.com/forum/showthread.php?t=35387)

\------------------------------

For direct GPU to FPGA communication,

[Direct GPU/FPGA Communication Via PCI Express](http://research.microsoft.com/
pubs/172730/20120625%20UCAA2012_Bittner_Ruf_Final.pdf)

> Parallel processing has hit mainstream computing in the form of CPUs, GPUs
and FPGAs. While explorations proceed with all three platforms individually
and with the CPU-GPU pair, little exploration has been performed with the
synergy of GPU-FPGA. This is due in part to the cumbersome nature of
communication between the two. This paper presents a mechanism for direct GPU-
FPGA communication and characterizes its performance in a full hardware
implementation.

\------------------------------------

**Papilio and Pipistrello**

For those interested in low-cost FPGA boards, here are two innovative designs
-

[Papilio](http://papilio.cc/)

Pipistrello - [design](http://pipistrello.saanlima.com/index.php?title=Welcome
_to_Pipistrello), [a blog review](http://www.element14.com/community/blogs
/alex-the-kidd/2013/02/06/pipistrello-rev-20-fpga-board)

<iframe width="560" height="315" src="http://www.youtube.com/embed/SC88QoWV_b8" frameborder="0"> </iframe>

For those interested in 7-series Xilinx, please take a look at [Zedboard with
Zynq](http://elinux.org/Zedboard)

\-------------------------------------

For design, use [Xilinx Web ISE](http://en.wikipedia.org/wiki/Xilinx_ISE)
until you cannot.

\--------------------------------------

**Memory controller**

[How to build reliable FPGA memory interface controllers without writing your
own RTL code!](http://eetimes.com/design/programmable-logic/4014823/How-to-
build-reliable-FPGA-memory-interface-controllers-without-writing-your-own-RTL-
code-)

[Spartan-6 FPGA Memory
Controller](http://www.xilinx.com/support/documentation/user_guides/ug388.pdf)

[DDR3 controller for
Spartan-6](http://www.ohwr.org/projects/ddr3-sp6-core/wiki)

\----------------------------

A cool page with many useful links -

[Embedded Linux](http://elinux.org/Main_Page)

