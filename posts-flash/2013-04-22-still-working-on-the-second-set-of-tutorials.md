---
title: Still Working on the Second Set of Tutorials
tags: []
categories:
- blog
---
We are still working on the second set of tutorials. Researching and writing
it turns out to be lot more work than we originally anticipated, but it has
been good fun so far. Also, our writing is interrupted by the final stage of
['bootstrapped genome project'](http://www.homolog.us/blogs/2013/03/26
/bootstrapped-genome-project-iv-more-on-triplicate-experiments/), which
involves quite a bit of text-parsing as well.
<!--more-->

Here is the theme for the tutorials. In it, we expect to present various
software and hardware concepts that programmers use to make bioinformatics
applications efficient. Many familiar topics such as hashing, Fib heaps,
binary trees, Burrows Wheeler transform are included, but to make our life
interesting, we are making the presentations more hardware-oriented. What does
that mean? It implies that instead of talking about algorithms as mathematical
constructs, we present them as flow of data through various parts of computer.

Conceptually we visualize a large computation like flow of water through many
pipes and channel. Data flows from hard-drive to memory to cache to register
to ALU and back, again and again. If one part is less optimally designed, data
gets stuck and program sucks. For example, some software constructs that
appear cool in CS books are not cache friendly. You may gain 2X coolness for
4X reduction in speed. Are we wringing the most out of our machines?

Another theme we tried to highlight is the functional equivalence of RAM and
hard-drive. A really really poor bioinformatician can replace 512 Gb RAM with
512 Gb hard-drive, and run an assembly. It is true that the program will run
many times slower, but you can choose Hadoop. Our discussions are meant to
help you appreciate the functional equivalence of Hadoop-based Contrail
assembler and RAM-based Velvet assembler at the conceptual level.

Here is the rough outline.

1\. The first section will present von Neumann computing architecture and
explain the differences between various programming languages - C, C++, Java,
PERL, python, etc.

2\. Second section will discuss CS constructs like hashing, Bloom filter,
graphs, suffix arrays, etc.

3\. Third section will cover SQL database, NoSQL, Hadoop, MPI, Condor, cloud
computing, etc.

4\. Fourth section will be on hardware. It will cover everything ranging from
SSD, large RAM, cache optimization, multi-processor, multi-core, GPU, FPGA.

The presentations are at very introductory level. Do not expect too much, if
you are already an expert. In fact, we do not know, whether there is an
audience for the tutorials outside those who know it all.

