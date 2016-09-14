---
title: Parallel de Bruijn Graph Construction and Traversal for de novo Genome Assembly
tags: []
categories:
- blog
---
We wrote about Meraculous assembler over two years back (see [Genome Assembly
MERmaid and Meraculous](http://www.homolog.us/blogs/blog/2012/08/16/genome-
assembly-mermaid-and-meraculous/)) and even then it was noteworthy for
implementing perfect hash data structure for storing the graph. Reader J. Zola
pointed out that the program improved significantly since then.
<!--more-->

> You should also point out that in SC 2014 Aydin Buluc et al. published what
is probably the most scalable parallel version of de Bruijn graph
construction. The algorithm has been designed for and incorporated into
Meraculous. More here: http://dl.acm.org/citation.cfm?id=2683642.

Readers can access the paper on scalable parallel dBG construction
[here](http://dl.acm.org/citation.cfm?id=2683642). Performance improvement
from days to seconds appears very impressive !

> De novo whole genome assembly reconstructs genomic sequence from short,
overlapping, and potentially erroneous fragments called reads. We study
optimized parallelization of the most time-consuming phases of Meraculous, a
state-of-the-art production assembler. First, we present a new parallel
algorithm for k-mer analysis, characterized by intensive communication and I/O
requirements, and reduce the memory requirements by 6.93. Second, we
efficiently parallelize de Bruijn graph construction and traversal, which
necessitates a distributed hash table and is a key component of most de novo
assemblers. We provide a novel algorithm that leverages one-sided
communication capabilities of the Unified Parallel C (UPC) to facilitate the
requisite fine-grained parallelism and avoidance of data hazards, while
analytically proving its scalability properties. Overall results show
unprecedented performance and efficient scaling on up to 15,360 cores of a
Cray XC30, on human genome as well as the challenging wheat genome, with
performance improvement from days to seconds.

