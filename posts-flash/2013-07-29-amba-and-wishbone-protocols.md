---
title: AMBA and Wishbone Protocols
tags: []
categories:
- blog
---
![](http://www.armadeus.com/wiki/uploads/thumb/7/7e/Wb_buttonled_top.png
/700px-Wb_buttonled_top.png)
<!--more-->

When you have a multi-chip design, eventually you will have to handle the
question of interactions between those chips. Following links may come out to
be handy.

**[Advanced Microcontroller Bus Architecture](http://en.wikipedia.org/wiki/Advanced_Microcontroller_Bus_Architecture)**

> The Advanced Microcontroller Bus Architecture (AMBA) is used as the on-chip
bus in system-on-a-chip (SoC) designs. Since its inception, the scope of AMBA
has gone far beyond microcontroller devices, and is now widely used on a range
of ASIC and SoC parts including applications processors used in modern
portable mobile devices like smartphones.

AMBA is a registered trademark of ARM Limited,[1] and is an open standard, on-
chip interconnect specification for the connection and management of
functional blocks in a System-on-Chip (SoC). It facilitates right-first-time
development of multi-processor designs with large numbers of controllers and
peripherals.

AMBA was introduced by ARM Ltd in 1996. The first AMBA buses were Advanced
System Bus (ASB) and Advanced Peripheral Bus (APB). In its 2nd version, AMBA
2, ARM added AMBA High-performance Bus (AHB) that is a single clock-edge
protocol. In 2003, ARM introduced the 3rd generation, AMBA 3, including AXI to
reach even higher performance interconnect and the Advanced Trace Bus (ATB) as
part of the CoreSight on-chip debug and trace solution. In 2010 the AMBA 4
specifications were introduced starting with AMBA 4 AXI4, then in 2011[2]
extending system wide coherency with AMBA 4 ACE. In 2013[3] the AMBA 5 CHI
(Coherent Hub Interface) specification was introduced, with a re-designed
high-speed transport layer and features designed to reduce congestion.

These protocols are today the de facto standard for 32-bit embedded processors
because they are well documented and can be used without royalties.

[Here](http://blog.chinaunix.net/uid-20846214-id-2413063.html) is a Chinese
blog with good description of AMBA protocol. It describes the handshaking well
with two nice figures.

**[Wishbone](http://en.wikipedia.org/wiki/Wishbone_\(computer_bus\))**

> The Wishbone Bus is an open source hardware computer bus intended to let the
parts of an integrated circuit communicate with each other. The aim is to
allow the connection of differing cores to each other inside of a chip. The
Wishbone Bus is used by many designs in the OpenCores project.

A large number of open-source designs for CPUs and auxiliary computer
peripherals have now been released with Wishbone interfaces. Many can be found
at OpenCores, a foundation that attempts to make open-source hardware designs
available.

Wishbone is intended as a "logic bus". It does not specify electrical
information or the bus topology. Instead, the specification is written in
terms of "signals", clock cycles, and high and low levels.

This ambiguity is intentional. Wishbone is made to let designers combine
several designs written in Verilog, VHDL or some other logic-description
language for electronic design automation. Wishbone provides a standard way
for designers to combine these hardware logic designs (called "cores").
Wishbone is defined to have 8, 16, 32, and 64-bit buses. All signals are
synchronous to a single clock but some slave responses must be generated
combinatorially for maximum performance. Wishbone permits addition of a "tag
bus" to describe the data. But reset, simple addressed reads and writes,
movement of blocks of data, and indivisible bus cycles all work without tags.

The Wishbone page of open-cores is
[here](http://opencores.org/opencores,wishbone).

\------------------------------------------------------------

**Also check:**

[A simple design with Wishbone bus](http://www.armadeus.com/wiki/index.php?tit
le=A_simple_design_with_Wishbone_bus)

[Open Core Protocol](http://en.wikipedia.org/wiki/Open_Core_Protocol)

[2003: AMBA vs Wishbone - "A word of advise. stay away from AMBA if you care
about performance. AMBA sucks when it comes to performance. We used it in one
of our design and regret ever using it. If you have more than 2 devices
sitting on your bus and if your devices need to use the bus frequently, then
try some other bus interconnect. AMBA is good for low speed and low
performance IO based devices. It does not hold candle to any other bus when it
comes to throughput."](http://www.edaboard.com/thread9319.html)

[We do not have any experience to tell whether that is true.]

[2011: AMBA AXI and OCP: Behind the
Standards](http://info.arteris.com/blog/bid/59646/AMBA-AXI-and-OCP-Behind-the-
Standards)

[2006 paper - A Survey of Three System-on-Chip Buses: AMBA, CoreConnect and
Wishbone](http://es.elfak.ni.ac.rs/Papers/ICEST%20'06.pdf)

[2012-13: Opencores thread on AXI to
Wishbone](http://opencores.org/forum,Cores,0,4688)

**On crossbars switch**

From Wishbone wiki -

> Wishbone adapts well to common topologies such as point-to-point, many-to-
many (i.e. the classic bus system), hierarchical, or even switched fabrics
such as crossbar switches. In the more exotic topologies, Wishbone requires a
bus controller or arbiter, but devices still maintain the same interface.

![crossbar](http://upload.wikimedia.org/wikipedia/en/d/db/Wishbone_cross_bar.j
pg)

[2002 MS Thesis - Design, Development, and Simulation/Experimental Validation
of a Crossbar Interconnection Network for a Single-Chip Shared Memory
Multiprocessor Architecture](http://www.engr.uky.edu/~heath/Masters_Proj_Repor
t_Venugopal_Duvvuri.pdf)

[Hardware design and implementation of a network-on-chip based high
performance crossbar switch Fabric](http://repository.tudelft.nl/view/ir/uuid
%3A2b95ac2a-09d7-4f14-ab08-864d33e61fea/)

> High-performance routers have the task of transmitting traffic in between
the nodes of the Internet, the network of networks that carries the vast
amount of information among billions of users. The switch fabric is the key
building block of every router, and various switch fabric architectures are
used in the market products. The crossbar-based switch fabric architectures
(both buffered and unbuffered) offer very high performances and are widely
used for high-performance routers. However their cost grows quadratically with
the input/output port count, since they require internal crosspoints (and
buffers) for every input/output port pair.

Recently, a functional-level design of two novel Network-on-Chip based switch
fabric architectures was proposed, Unidirectional NoC (UDN) and
Multidirectional NoC (MDN), as a replacement of the buffered crossbar switch
fabric architecture. In this thesis, we propose the hardware design and
implementation of the aforementioned architectures for the FPGA platform. We
further improve the routing and scheduling algorithms of these architectures
for feasible hardware design. The synthesis and simulations are carried out
over a wide range of switch sizes and traffic scenarios. The simulation
results are also validated on the FPGA platform, by generating pseudo-random
destination addresses for the packets on LFSR based test modules. The results
show that UDN outperforms MDN in terms of throughput, whereas MDN offers
greater performance-cost ratio. Both architectures offer scalability,
flexibility and high performance, confirming the ideas in the original
proposal.

[Design and implementation of high-speed buffered crossbars with efficient
load balancing for multi-core SoCs](http://dl.acm.org/citation.cfm?id=1850941)

> A large increase of the number of devices integrated in a single chip in
conjunction with the significant demands of modern applications for
performance has led the designers to a system development methodology based on
integrating multiple pre-verified intellectual property cores. Yet, design
productivity requirements push designers to focus on key micro-architectural
solutions to manage more efficiently the scaling of multi-core SoCs as well as
to increase the degree of design automation, particularly as rapid prototyping
using reconfigurable computing is becoming mainstream. In this paper we
present a novel interconnect architecture based on optimized components to
efficiently manage SoCs that follow either a multi-core based approach or are
built to support SIMD-style applications that can exploit the processing power
of a pool of hardware resources; first we analyze the design of a crossbar
featuring shared-memory combined input-crosspoint buffering as a solution for
efficient implementation of on-chip interconnection; second we describe the
design of a load-balancer featuring configurable proportional allocation of
on-chip resources and in-order delivery as a solution for efficient scheduling
and execution of processing tasks. The main focus of the paper is to describe
and evaluate the mechanisms designed to distribute and manage data transfers
so as to implement an efficient interconnection of the integrated cores and
control access to available (either on-chip or off-chip) resources for the
implementation of a number of embedded systems and applications. Each of these
challenges is handled by the proposed architecture in an efficient way in
terms of performance, cost in silicon and flexibility.

Is that too much for bioinformaticians? Should we switch to our regular
channels of #ENCODE or genome assembly?

