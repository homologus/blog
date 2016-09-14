---
title: Fastest Way to Reverse Complement a Sequence
tags: []
categories:
- blog
---
Kai Blin asked how fast reverse complementing is in various languages.
<!--more-->

![Capture](http://www.homolog.us/blogs/wp-
content/uploads/2013/05/Capture9-300x65.png)

The answer not only depends on the language, but also on the algorithm as well
as the hardware.

Speaking of algorithms to reverse a byte, we mentioned [this Stanford website]
(http://graphics.stanford.edu/~seander/bithacks.html#BitReverseObvious) few
months back. It is low level designers' paradise. Also do not miss [this
stackoverflow thread](http://stackoverflow.com/questions/746171/best-
algorithm-for-bit-reversal-from-msb-lsb-to-lsb-msb-in-c) that discusses
hardware dependence of the algorithms.

As we discussed in [What They Never Teach You in Programming
Classes](http://www.homolog.us/blogs/2012/10/31/what-they-never-teach-you-in-
programming-classes/), if Intel designs a 'bioinformatics co-processor',
nobody will need to write fancy reverse complement code any more.

Edit.

Readers may find the following pages useful.

1\. [Stanford 'bit twiddling' website](http://graphics.stanford.edu/~seander/b
ithacks.html#BitReverseObvious) mentioned above.

a) Reverse bits the obvious way

b) Reverse bits in word by lookup table

c) Reverse the bits in a byte with 3 operations (64-bit multiply and modulus
division)

d) Reverse the bits in a byte with 4 operations (64-bit multiply, no division)

e) Reverse the bits in a byte with 7 operations (no 64-bit)

f) Reverse an N-bit quantity in parallel in 5 * lg(N) operations

Stackoverflow page has benchmarks of above options.

2\. EDAboard question - [How to reverse the bits in a
byte?](http://www.edaboard.com/thread191928.html)

> Because no microcontroller has a built in hardware instruction for bit
reversal, you usually do it in a loop, utilizing shift instructions. I guess,
you can easily figure out the C code for the operation.

The fastest method is however a ROM table of 256 bytes, that holds the
reversed code for each possible input byte.

3\. Paper - [Bit-level optimization for high-level synthesis and FPGA-based
acceleration](http://www.researchgate.net/publication/221225119_Bit-
level_optimization_for_high-level_synthesis_and_FPGA-based_acceleration)

> ABSTRACT Automated hardware design from behavior-level abstraction has drawn
wide interest in FPGA-based acceleration and configurable computing research
field. However, for many high-level programming languages, such as C/C++, the
description of bitwise access and computation is not as direct as hardware
description languages, and high-level synthesis of algorithmic descriptions
may generate suboptimal implementations for bitwise computation-intensive
applications. In this paper we introduce a bit-level transformation and
optimization approach to assisting high-level synthesis of algorithmic
descriptions. We introduce a bit-flow graph to capture bit-value information.
Analysis and optimizing transformations can be performed on this
representation, and the optimized results are transformed back to the standard
data-flow graphs extended with a few instructions representing bitwise access.
This allows high-level synthesis tools to automatically generate circuits with
higher quality. Experiments show that our algorithm can reduce slice usage by
29.8% on average for a set of real-life benchmarks on Xilinx Virtex-4 FPGAs.
In the meantime, the clock period is reduced by 13.6% on average, with an
11.4% latency reduction.

