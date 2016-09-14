---
title: Wait-free and Lock-free Queues
tags: []
categories:
- blog
---
We have been reading the technical papers on algorithms, which take advantage
of 'compare-and-swap' feature built in processor hardware to properly scale in
multi-processor environment. The k-mer counting program Jellyfish is one of
those. In this context, readers may find the following links and papers
useful.
<!--more-->

1\. [Wikipedia - compare and swap](http://en.wikipedia.org/wiki/Compare-and-
swap)

> In computer science, compare-and-swap (CAS) is an atomic instruction used in
multithreading to achieve synchronization. It compares the contents of a
memory location to a given value and, only if they are the same, modifies the
contents of that memory location to a given new value. This is done as a
single atomic operation. The atomicity guarantees that the new value is
calculated based on up-to-date information; if the value had been updated by
another thread in the meantime, the write would fail. The result of the
operation must indicate whether it performed the substitution; this can be
done either with a simple Boolean response (this variant is often called
compare-and-set), or by returning the value read from the memory location (not
the value written to it).

2\. [Simple, fast, and practical non-blocking and blocking concurrent queue
algorithms - Michael and Scott
(1996)](http://www.cs.rochester.edu/~scott/papers/1996_PODC_queues.pdf)

> Drawing ideas from previous authors, we present a new non-blocking
concurrent queue algorithm and a new two-lock queue algorithm in which one
enqueue and one dequeue can proceed concurrently. Both algorithms are simple,
fast, and practical; we were surprised not to find them in the literature.
Experiments on a 12-node SGI Challenge multiprocessor indicate that the new
non-blocking queue consistently outperforms the best known alternatives; it is
the clear algorithm of choice for machines that provide a universal atomic
primitive (e.g. compare-and-swap or load-linked/store-conditional). The two-
lock concurrent queue outperforms a single lock when several processes are
competing simultaneously for access; it appears to be the algorithm of choice
for busy queues on machines with non-universal atomic primitives (e.g. test-
and-set). Since much of the motivation for non-blocking algorithms is rooted
in their immunity to large, unpredictable delays in process execution, we
report experimental results both for systems with dedicated processors and for
systems with several processes multiprogrammed on each processor.

3\. [A Methodology for Creating Fast Wait-Free Data Structures - Kogan and
Petrank (2012)](http://www.cs.technion.ac.il/~erez/Papers/wf-methodology-
ppopp12.pdf)

The 1996 paper by Michael and Scott is really fascinating, because the
algorithm is simple but elegant. In fact, the Petrank group tried to find
better alternate algorithms for their wait-free queues, but then fell back on
to the ~17 year old method. We will add more on the topic in a follow-up
commentary.

