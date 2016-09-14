---
title: 'Scrm: efficiently simulating long sequences using the approximated coalescent
  with recombination'
tags: []
categories:
- blog
---
[Link](http://bioinformatics.oxfordjournals.org/content/early/2015/01/08/bioin
formatics.btu861.short?rss=1)
<!--more-->

> Motivation: Coalescent based simulation software for genomic sequences
allows the efficient in silico generation of short and medium-sized genetic
sequences. However, the simulation of genome-size data sets as produced by
Next-Generation sequencing (NGS) is currently only possible using fairly crude
approximations.

Results: We present the Sequential Coalescent with Recombination Model (SCRM),
a new method that efficiently and accurately approximates the coalescent with
recombination, closing the gap between current approximations and the exact
model. We present an efficient implementation and show that it can simulate
genomic-scale data sets with an essentially correct linkage structure.

Availability: The open source implementation scrm is freely available at
https://scrm.github.io under the conditions of the GPLv3 license.

