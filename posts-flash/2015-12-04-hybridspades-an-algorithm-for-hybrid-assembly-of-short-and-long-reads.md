---
title: 'HYBRIDSPADES: an algorithm for hybrid assembly of short and long reads'
tags: []
categories:
- blog
---
[You pay to read](http://bioinformatics.oxfordjournals.org/content/early/2015/
11/20/bioinformatics.btv688) \-
<!--more-->

> Motivation: Recent advances in single molecule real-time (SMRT) and nanopore
sequencing technologies have enabled high-quality assemblies from long and
inaccurate reads. However, these approaches require high coverage by long
reads and remain expensive. On the other hand, the inexpensive short reads
technologies produce accurate but fragmented assemblies. Thus, a hybrid
approach that assembles long reads (with low coverage) and short reads has a
potential to generate high-quality assemblies at reduced cost.

Results: We describe HYBRIDSPADES algorithm for assembling short and long
reads and benchmark it on a variety of bacterial assembly projects. Our
results demonstrate that HYBRIDSPADES generates accurate assemblies (even in
projects with relatively low coverage by long reads) thus reducing the overall
cost of genome sequencing. We further present the first complete assembly of a
genome from single cells using SMRT reads.

Availability and implementation: HYBRIDSPADES is implemented in C++ as a part
of SPAdes genome assembler and is publicly available at
http://bioinf.spbau.ru/en/spades

Readers may also check -

[Very Efficient Hybrid Assembler for PacBio
Data](http://www.homolog.us/blogs/blog/2014/10/13/very-efficient-hybrid-
assembler-for-pacbio-data/)

