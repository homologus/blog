---
title: Mapping to a Graph-style Reference Genome  - Arxiv Paper
tags: []
categories:
- blog
---
David Haussler and colleagues had been working on how to align a new read
library against thousands of human genomes. The easy solution of performing
the same alignment thousand times does not scale well. Benedict Paten, Adam
Novak and David Haussler posted [a new paper in
arxiv](http://arxiv.org/ftp/arxiv/papers/1404/1404.5010.pdf) to address this
question. This appears like an interesting paper, but we have not read it
carefully to understand the innovation beyond what Juni Siren (corrected) and
others proposed before.
<!--more-->

> To support comparative genomics, population genetics, and medical genetics,
we propose that a reference genome should come with a scheme for mapping each
base in any DNA string to a position in that reference genome. We refer to a
collection of one or more reference genomes and a scheme for mapping to their
positions as a reference structure. Here we describe the desirable properties
of reference structures and give examples. To account for natural genetic
variation, we consider the more general case in which a reference genome is
represented by a graph rather than a set of phased chromosomes; the latter is
treated as a special case.

Readers may also find the following work from Haussler group relevant -

[HAL: a Hierarchical Format for Storing and Analyzing Multiple Genome
Alignments](http://www.homolog.us/blogs/blog/2013/05/22/hal-a-hierarchical-
format-for-storing-and-analyzing-multiple-genome-alignments/)

Edit.

Speaking of Juni Siren's algorithm, following twitter discussions are relevant
-

![Capture](http://www.homolog.us/blogs/wp-
content/uploads/2014/04/Capture16-300x177.png)

