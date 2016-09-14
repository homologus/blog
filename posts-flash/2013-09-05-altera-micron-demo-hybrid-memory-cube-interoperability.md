---
title: Altera, Micron Demo Hybrid Memory Cube Interoperability
tags: []
categories:
- blog
---
Remember [Craig Barrett's breakfast
party](http://www.homolog.us/blogs/blog/2013/05/05/the-future-of-computers-
multicore-and-the-memory-wall/)? [A new
fridge](http://www.digitimes.com/news/a20130905PR202.html) is found.
<!--more-->

[Hybrid Memory Cube from
wiki](http://en.wikipedia.org/wiki/Hybrid_Memory_Cube):

![](http://www.legitreviews.com/wp-content/uploads/2013/09/hmc_layers.jpg)

> Hybrid Memory Cube (HMC) is a new type of computer RAM technology developed
by Micron Technology. The Hybrid Memory Cube Consortium (HMCC) is backed by
several major technology companies including Samsung, Micron Technology, ARM,
HP, Microsoft, Altera, and Xilinx.[1]

HMC uses 3D packaging of multiple memory dies, typically 4 or 8 memory dies
per package,[2] with using of through-silicon vias (TSV) and microbumps. It
has more data banks than classic DRAM memory of the same size. Memory
controller is integrated into memory package as separate logic die.[3] HMC
uses standard DRAM cells but its interface is incompatible with current DDRn
(DDR2 or DDR3) implementations.[4]

HMC technology won Best New Technology award from The Linley Group (publisher
of Microprocessor Report magazine) in 2011.[5][6]

First public specification, HMC 1.0 was published in April 2013.[7] According
to it, HMC uses 16-lane or 8-lane (half size) full-duplex differential serial
links, with each lane having 10, 12.5 or 15 Gbit/s SerDes.[8] Each HMC package
is named cube, they can be chained in network of up to 8 cubes with cube-to-
cube links and some cubes using their links as pass-thru link.[9] Typical cube
package with 4 links has 896 BGA pins and sized 31x31x3,8 millimeters.[10]

Typical raw bandwidth of single 16-lane link with 10 Gbit/s signalling is 40
GB/s (20 GB/s transmit and 20 GB/s receive); cubes with 4 and 8 links are
planned. Effective memory bandwidth utilization varies in 50%-33% for smallest
packets of 32 bytes; and in 85%-45% for 128 bytes.[2]

As reported at HotChips 23 conference in 2011, first generation of HMC
demonstration cube with four 50 nm DRAM memory dies and one 90 nm logic die
with total capacity of 512 MB and size 27x27 mm had power consumption of 11 W
and was powered with 1.2 V.[2]

Engineering samples of 2nd Generation HMC memory chips are expected in summer
2013 by Micron and mass production of HMC may start in 2014.

