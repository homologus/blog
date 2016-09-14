---
title: Memory Bandwidth and Recursive Variable Expansion - PhD Thesis of Zubair Nawaz
tags: []
categories:
- blog
---
We are studying the PhD thesis of Zubair Nawaz titled ["Recursive Variable
Expansion: A Transformation for Reconfigurable Computing"](http://ce-
publications.et.tudelft.nl/publications/116_recursive_variable_expansion.pdf)
at TU Delft, because the following claim caught our attention.
<!--more-->

> We show that our technique can reduce the memory bandwidth requirement from
49.36 Gb/sec to 8 Kb/sec even for existing approaches.

As we mentioned many times, memory bandwidth has become the biggest bottleneck
in the kind of developments we are doing. The best analogy was ten cooks
getting eggs from the fridge at the kitchen of Intel ex-CEO.

[The Future of Computers Multicore and the Memory
Wall](http://www.homolog.us/blogs/blog/2013/05/05/the-future-of-computers-
multicore-and-the-memory-wall/)

In our case, the fridge is the memory and cooks are the processors. We read
the [recently published SOAP3-dp paper](http://www.plosone.org/article/info%3A
doi%2F10.1371%2Fjournal.pone.0065632) carefully and found the authors to
struggle with the same problem. Of course, they were there years before us,
and came up with three clever tricks -

**1\. Optimization of parallel access to the GPU global memory**

> SOAP3 makes use of the 2way-BWT indexing technique [23] and involves random
access to the indexing data structures in the main memory. The original design
of 2way-BWT [5] was based on two-level sampling. The design works well for CPU
but not in the highly parallel environment of GPU. The data structures are too
large and must be placed into the global memory of GPU, causing serious memory
contention among the processors inside the GPU. For this purpose, in SOAP3,
the index is redesigned to use one-level sampling instead, which greatly
reduces the number of memory accesses by half.

Apart from reducing the number of global memory accesses, we also optimize the
time of individual access to the global memory. This is achieved by coalescing
simultaneous global memory accesses.

...

In SOAP3-dp, we try to coalesce as many memory accesses as possible. The
global memory of GPU device holds two large data structures the 2way-BWT
index, and the set of reads. To enable coalesced access. the set of reads is
partitioned into groups of 32 (equals the warp size). .....These coalesced
accesses could be done in a single memory transaction with only one time of
memory address interpretation, achieving excellent memory throughput.

**2\. Divergence control and 3-level stratified alignment pipeline**

> GPU works in a single-instruction multiple-thread (SIMT) mode. Processors in
the same SM must execute the same instruction at one time. When mismatches are
allowed, a read can have more than one branch during alignment. Too many
diverging branches however would lower the efficiency of GPU drastically,
because most processors (with few branches) may become idle and wait for a few
others. For this purpose, we derive a suffix array (SA) ranges count based
parameter, which can be determined at runtime, whether a read would generate
too many branches, and reads are classified into different levels of
complexity according to this parameter. The basic idea is that reads of
different levels should be aligned separately. In SOAP3-dp's implementation,
we have designed three levels of complexity. For the all best output
parameter, which outputs all alignment results equally the best, if 2
mismatches are allowed, the SA ranges count dividing the three levels are 4
and 32 respectively (it means that, during alignment, a read with SA ranges
count exceeding a threshold after extending a base, will be stopped and
scheduled for next level, thresholds for other mismatch allowances and output
parameters are included in the definition.h file in the source code). In
particular, we let the GPU handle the first two levels, and use the CPU to
take care of the most complicated reads (which account for a small percentage
only). Furthermore, to fully utilize both GPU and CPU processing power, SOAP3
overlaps the alignment of complicated reads from the previous batch in CPU
with the alignment of the next batch in GPU (as shown in the Figure S4 in File
S1).

**3\. GPU-accelerated dynamic programming**

Here they rewrote Smith-Waterman.

**4\. Effort Limit for Dynamic Programming 

5\. Paired-end alignment

6\. Scoring functions**

We do not understand all solutions yet, but we are happy to at least reach the
same problem as them.

\------------------------------------------------------

Getting back to recursive variable expansion, how does it reduce the memory
bandwidth requirement so much? Apparently by not sending data and back and
forth between processor and FPGA.

> In the last chapter, we saw that there are two stages in Smith-Waterman (SW)
algorithm namely matrix fill and traceback. First, we fill the matrix with

optimal score found, then we find the maximum of the optimal score. Finally we
perform the traceback starting from the maximum value. This procedure is
performed for all the sequences in the database. Since the matrix fill stage
takes 98.6% of the overall time [110], all FPGA implementations use FPGAs for
accelerating the matrix fill stage.

There are two methods to perform the sequence alignment on a reconfigurable
system. In the first method, the matrix is filled on an FPGA and then the
matrix data is sent to the GPP, where the traceback is performed. This method
creates a memory bottleneck in any off-the-shelf FPGA board. In the second
method, a sequence is shortlisted by finding the maximum value after
performing the matrix fill stage for the whole database. Later, that maximum
value and the index of the corresponding sequence is transferred to the GPP.
The matrix fill stage for the shortlisted sequences is repeated on the GPP and
the traceback is performed to get the optimal alignment.

In this chapter, we propose a parallel FPGA design of the SW traceback, which
performs the alignment immediately after completing the matrix fill for all
the sequences in the database. This way, we can avoid the second matrix fill
stage for the shortlisted sequences at the expense of more area consumption.

Parallel implementation of bioinformatics algorithms is a fascinating
exercise. As we continue, we seem to find ourselves more compelled to view the
algorithms as spatio-temporal dynamics of data moving between processing
blocks and memory. In that mode of operation, algorithms are not static
mathematical construct, but are highly dependent on the relative sizes of
various 'pipes' through with data is moving from one place to another.

