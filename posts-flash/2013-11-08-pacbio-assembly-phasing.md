---
title: Pacbio Assembly and Phasing
tags: []
categories:
- blog
---
Jason Chin, who wrote the HGAP assembler for PacBio-based genome assemble, is
on to a more difficult problem. Here are his slides from the recent CSHL
conference -
<!--more-->

\------------------------------------------------

Readers of our blog surely knows that a different way for doing these things
was published last year. Please do not tell him :)

[HapCompass: An Elegant Use of Graphs for Haplotype
Assembly/Phasing](http://www.homolog.us/blogs/blog/2012/08/28/hapcompass-an-
elegant-use-of-graphs-for-haplotype-assemblyphasing/)

>

The novelty of HapCompass is to create a different kind of graph (named
compass in the paper) that assigns SNPs as nodes and linking paired-end
sequences as edges. In the following figure, if two SNPs come from the same
chromosome, they will be linked by an edge. If not, no edge will exist between
them. Of course, the previous statement assumes complete error-free world. Few
spurious edges can be created by noisy sequence data.

![](http://www.homolog.us/blogs/wp-content/uploads/2012/08/haplo2-300x173.png)

Based on the above graph structure, the authors translated the
phasing/haplotype assembly problem into a spanning tree problem, and solved it
through a minimum weight edge removal optimization algorithm.

