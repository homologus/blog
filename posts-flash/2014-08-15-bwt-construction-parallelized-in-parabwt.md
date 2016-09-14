---
title: BWT Construction Parallelized in 'Parabwt'
tags: []
categories:
- blog
---
Last year, we commented that a large number of bioinformatics groups were
working on constructing BWT from huge Illumina libraries. The group of
Yongchao Liu, Thomas Hankeln and Bertil Schmidt (who previously worked on
various GPU algorithms) was not mentioned, but they also joined the fray with
[their parabwt release](http://parabwt.sourceforge.net/homepage.htm#latest).
<!--more-->

> ParaBWT is a new and practical parallelized Burrows-Wheeler transform (BWT)
and suffix array construction algorithm for big genome data, which has a
linear space complexity with a small constant factor. The performance of
ParaBWT has been evaluated using two sequences generated from two human genome
assemblies: the Ensembl Homo sapiens assembly and the human reference genome,
on a workstation with two Intel Xeon X5650 hex-core CPUs and 96 GB RAM,
running the Ubuntu 12.04 LTS operating system. Our performance comparison to
FMDindex and Bwt-disk reveals that on 12 CPU cores, ParaBWT runs up to 2.2
times faster than FMD-index, reducing the runtime from 26.56 hours to 12.34
hours for a sequence of about 60 billion nucleotides, and up to 99.0 times
faster than Bwt-disk.

Paper is still forthcoming. Please be satisfied with the sourceforge page for
the time being.

