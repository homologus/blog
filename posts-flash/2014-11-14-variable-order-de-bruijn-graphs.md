---
title: Variable-Order de Bruijn Graphs
tags: []
categories:
- blog
---
Today's must read algorithm paper ! It describes the theory behind -[MEGAHIT:
An Ultra-fast Single-node Solution for Large and Complex Metagenomics Assembly
via Succinct de Bruijn Graph ](http://www.homolog.us/blogs/blog/2014/09/25
/megahit-an-ultra-fast-single-node-solution-for-large-and-complex-
metagenomics-assembly-via-succinct-de-bruijn-graph/). [Correction: The
algorithm is an improvement over MEGAHIT. Please see comment section.]
<!--more-->

> **Our Contribution.** SPAdes [2] and IDBA [21] represent the state-of-the-
art for genome assemblers, producing assemblies of greatly improved quality
compared to previous approaches. However, their need to construct several de
Bruijn graphs of different orders over the assembly process makes them
extremely slow on large genomes. In this paper we address this problem by
describing a succinct data structure that, for a given K, eciently represents
all the de Bruijn graphs for k K and allows navigation within and between each
graph. We have implemented our data structure and show that in practice it
requires around twice the space of a graph for a single K, and incurs a modest
slow down in construction time and on navigation operations.

![Capture](http://www.homolog.us/blogs/wp-
content/uploads/2014/11/Capture5-300x37.png)

[Link](http://arxiv.org/abs/1411.2718)

> The de Bruijn graph GK of a set of strings S is a key data structure in
genome assembly that represents overlaps between all the K-length substrings
of S. Construction and navigation of the graph is a space and time bottleneck
in practice and the main hurdle for assembling large, eukaryote genomes. This
problem is compounded by the fact that state-of-the-art assemblers do not
build the de Bruijn graph for a single order (value of K) but for multiple
values of K. More precisely, they build d de Bruijn graphs, each with a
specific order, i.e., GK1,GK2,,GKd. Although, this paradigm increases the
quality of the assembly produced, it increases the memory by a factor of d in
most cases. In this paper, we show how to augment a succinct de Bruijn graph
representation by Bowe et al. (Proc. WABI, 2012) to support new operations
that let us change order on the fly, effectively representing all de Bruijn
graphs of order up to some maximum K in a single data structure. Our
experiments show our variable-order de Bruijn graph only modestly increases
space usage, construction time, and navigation time compared to a single order
graph.

