---
title: What is Faster - CPU, GPU or FPGA? Our Investigation of Leading Alignment Algorithms
  - (ii)
tags: []
categories:
- blog
---
This commentary provides you with a general introduction of the three hardware
technologies without referring to any bioinformatics algorithm.
<!--more-->

**How does a Computing Chip Work?**

In two earlier commentaries, we explained how a traffic signal light chip is
designed.

[Designing a Traffic Signal
Light](http://www.homolog.us/blogs/blog/2013/05/29/designing-a-traffic-signal-
light/)

[Designing a Traffic Signal Light
II](http://www.homolog.us/blogs/blog/2013/06/07/designing-a-traffic-signal-
light-ii/)

Every digital chip is designed following similar rules. Only differences are
in the details and the level of complexity.

**Software vs Hardware**

In the design of a computer chip, the designer has the option to make the
design flexible enough so that few variable parameters can be controlled
externally. For example, let us say the designer of the traffic signal light
chip builds it in such a way that users can later adjust how long yellow light
stays on compared to red or green. That is 'software control'. Hardware
control, on the other hand, means everything is hard-coded within the chip.

![](http://us.123rf.com/400wm/400/400/alexmit/alexmit1210/alexmit121000011/156
03504-computer-chips-isolated-on-white.jpg)

A computer chip is a black box (see figure) and those externally controls take
place by passing electric signal through one of those legs of the chip.
'Software programming' is essentially the way to modulate the signals on those
legs. Software control gives immense flexibility to the users of the chips,
but often at the cost of speed. The loss of speed comes from the design
flexibility built into hardware design.

Also it is less understood that the entire thinking of the software world
(known as 'computer science') has been been shaped by the underlying hardware
technology. When you pick up a computer science book and read about various
algorithms (suffix array, hashing, sorting, etc.) you may think that they are
general mathematical methods to be applicable everywhere. In reality, they are
reflections of von Neumann architecture being used in CPU architecture.

The above observation has several ramifications -

(i) Moving from one hardware technology to another is not only a matter of re-
coding the algorithm for a different architecture. It requires new thinking.

(ii) Even within the CPU world, it is becoming difficult to go from one core
to multi-core due to basic algorithm-level limitations. Von Neumann
architecture is highly biased toward single processing unit.

(iii) The code and performance can change dramatically, when Intel modifies
its core set of CPU codes. All those hardware level details are hidden in
'hash function', which computer science professors stops investigating over a
decade back and left to the industrial users and bioinformaticians, for whom
performance is more important than mathematical elegance of algorithm.

[Why Computer Science Professors Dislike Hash
Functions](http://www.homolog.us/blogs/blog/2013/05/06/why-computer-science-
professors-dislike-hash-functions/)

[NGS Assembly Programs What Hash Functions Do They
Use?](http://www.homolog.us/blogs/blog/2013/05/07/genome-assembly-programs-
what-hash-functions-do-they-use/)

[Perfect Hash Algorithm of Meraculous
Assembler](http://www.homolog.us/blogs/blog/2012/10/02/perfect-hash-algorithm-
of-meraculous-assembler/)

[Hardware-based Hash Functions](http://www.homolog.us/blogs/blog/2013/04/28
/hardware-based-hash-functions/)

\----------------------------------------------------------------------

**CPU**

About a decade years back, 'CPU' referred to a large spectrum of computing
chips developed by various companies to execute the von Neumann architecture.
Today the description only includes Intel's processor with AMD remaining as a
distant competitor. Intel's victory has been purely due to economic reasons.
It was the only company, which managed to scale up its fabrication technology
and commoditize the processor market.

The other companies, who lost the processor market, has been using their
technical excellence in power consumption to come up with embedded board
alternatives such as Raspberry Pi, or are staying relevant in the mobile-
computing market.

Someone interested in understanding the difference between CPU, GPU and FPGA
needs to [understand the von Neumann architecture in
detail](http://en.wikipedia.org/wiki/Von_Neumann_architecture).

> The term Von Neumann architecture, also known as the Von Neumann model or
the Princeton architecture, derives from a 1945 computer architecture
description by the mathematician and early computer scientist John von Neumann
and others, First Draft of a Report on the EDVAC[1]. This describes a design
architecture for an electronic digital computer with subdivisions of a
processing unit consisting of an arithmetic logic unit and processor
registers, a control unit containing an instruction register and program
counter, a memory to store both data and instructions, external mass storage,
and input and output mechanisms.[1][2] The meaning of the term has evolved to
mean a stored-program computer in which an instruction fetch and a data
operation cannot occur at the same time because they share a common bus. This
is referred to as the Von Neumann bottleneck and often limits the performance
of the system.[3]

The design of a Von Neumann architecture is simpler than the more modern
Harvard architecture which is also a stored-program system but has one
dedicated set of address and data buses for reading data from and writing data
to memory, and another set of address and data buses for fetching
instructions.

A stored-program digital computer is one that keeps its programmed
instructions, as well as its data, in read-write, random-access memory (RAM).
Stored-program computers were an advancement over the program-controlled
computers of the 1940s, such as the Colossus and the ENIAC, which were
programmed by setting switches and inserting patch leads to route data and to
control signals between various functional units. In the vast majority of
modern computers, the same memory is used for both data and program
instructions, and the Von Neumann vs. Harvard distinction applies to the cache
architecture, not main memory.

**GPU**

The weakness of CPU architecture in parallel processing was apparent from the
early days in display units of computers, because human eye is highly
sensitive to any apparent discrepancy in graphical rendering of information.
An ecosystem of companies developed to address the needs of video games
market, and [Nvidia emerged as a
competitor](https://en.wikipedia.org/wiki/Graphics_processing_unit) to Intel.

> In the early- and mid-1990s, CPU-assisted real-time 3D graphics were
becoming increasingly common in computer and console games, which led to an
increasing public demand for hardware-accelerated 3D graphics. Early examples
of mass-marketed 3D graphics hardware can be found in fifth generation video
game consoles such as PlayStation and Nintendo 64. In the PC world, notable
failed first tries for low-cost 3D graphics chips were the S3 ViRGE, ATI Rage,
and Matrox Mystique. These chips were essentially previous-generation 2D
accelerators with 3D features bolted on. Many were even pin-compatible with
the earlier-generation chips for ease of implementation and minimal cost.
Initially, performance 3D graphics were possible only with discrete boards
dedicated to accelerating 3D functions (and lacking 2D GUI acceleration
entirely) such as the 3dfx Voodoo. However, as manufacturing technology
continued to progress, video, 2D GUI acceleration, and 3D functionality were
all integrated into one chip. Rendition's Verite chipsets were the first to do
this well enough to be worthy of note.

NVidia's GPU chips contain hundreds of simple processing units, each driving a
display region on the monitor. NVidia later added a set of APIs to allow users
program those chips and use them for general purpose computing. Please check
[General-purpose computing on graphics processing units
(GPGPU)](http://en.wikipedia.org/wiki/General-
purpose_computing_on_graphics_processing_units) for more details.

**FPGA**

Above debates about architecture and programming language would be
unnecessary, if everyone could built a computer chip customized for his task
and then program it to fine-tune the performance. Unfortunately, fabricating a
custom chip is very expensive.

FPGA technology from Xilinx and Altera removes the fabrication problem by
designing generic chips customizable through hardware level programming. FPGAs
contain gates and building blocks, whose connections are reprogrammed by
passing electric signals into them. The reprogrammed chip can then be used
just like a Intel chip. Pretty cool, eh?

Please do not forget that you will do diddly squat, if we give you an Intel
chip. The chip needs to come in a board (motherboard) with memory and other
useful units before we can start talking. For grandmas and most python
programmers, the board needs to come packaged within a large and generally
trouble free box.

The same is true for FPGA chips. You need to get them in the form of cards or
complete boxes. The process can be ad maddening as trying to select a shampoo
from the supermarket isle given how many variations of FPGA chips and boards
are around.

\-----------------------------------------------------------------------------
---------
