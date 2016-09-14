---
title: A Graph Extension of the Positional Burrows-Wheeler Transform and its Applications
tags:
- algorithm
- bwt
- graph
categories:
- blog
---
[from biorxiv](http://biorxiv.org/content/early/2016/05/02/051409)
<!--more-->

> We present a generalization of the Positional Burrows-Wheeler Transform
(PBWT) to genome graphs, which we call the gPBWT. A genome graph is a
collapsed representation of a set of genomes described as a graph. In a genome
graph, a haplotype corresponds to a restricted form of walk. The gPBWT is a
compressible representation of a set of these graph-encoded haplotypes that
allows for efficient subhaplotype match queries. We give efficient algorithms
for gPBWT construction and query operations. We describe our implementation,
showing the compression and search of 1000 Genomes data. As a demonstration,
we use the gPBWT to quickly count the number of haplotypes consistent with
random walks in a genome graph, and with the paths taken by mapped reads;
results suggest that haplotype consistency information can be practically
incorporated into graph-based read mappers.

