---
title: 'Parallelization Horror Story: How Not to Run String Graph Assembler'
tags: []
categories:
- blog
---
On June 2, we started running String Graph Assembler on a genomic data set
with a genome size of about 700 Mb. The contig assembly finished at the early
hours of July 11. Yes, that is one month and nine days, and we still need to
do the scaffolding. What went wrong?
<!--more-->

It was that we did not run the program in the way its author Jared Simpson
recommended us to do, or otherwise it could have finished many eons ago. We
contacted him early in the process telling that his program was running too
slow, and Jared explained that we were running it on too many processors. SGA
has an option to suggest the number of processors/threads to execute the code
and we picked 32, which was the max for our server.

`

# The number of threads to use

CPU=32

`

Jared recommended us to reduce the number to around 12. However, we continued
the execution for the sake of benchmarking the difference between different
processor counts.

How can reducing the degree of parallel execution improve performance? It is a
problem we explained earlier in [The Future of Computers Multicore and the
Memory Wall](http://www.homolog.us/blogs/blog/2013/05/05/the-future-of-
computers-multicore-and-the-memory-wall/). You can imagine 32 processors as 32
cooks, who all need to go to the refrigerator (memory bank) to get data before
performing the next step of cooking. Heng Li's RLBWT improvement made SGA
extremely fast, and you can make an analogy with buying a high-tech oven that
boils an egg in seconds. What are the cooks doing with arrival of the new
oven? All 32 of them are mostly lining up near the fridge to get more eggs,
and spending very little time in actual cooking !!

We will get to the same theme, when we discuss the implementation of various
alignment programs in CPU, GPU and FPGA, and also to answer a question from
reader Mikael Huss on parallel execution of de Bruijn graph assemblers. In
case of alignment, BGI was at first surprised, when direct implementation of
2BWT algorithm on GPU from CPU resulted in slower performance even though the
GPU had higher degree of parallel execution. They had to change the algorithm
to improve memory bandwidth, and that improvement is the core part of
[Ruibang's SOAP3-dp paper](http://www.plosone.org/article/info%3Adoi%2F10.1371
%2Fjournal.pone.0065632).

