---
title: 'CLARK: fast and accurate classification of metagenomic and genomic sequences
  using discriminative k-mers'
tags: []
categories:
- blog
---
Today's [new metagenome
classifier](http://www.biomedcentral.com/1471-2164/16/236/abstract). We need
to read, whether the novel approach is a brand new algorithm or implementation
of existing ones.
<!--more-->

>

Background: The problem of supervised DNA sequence classification arises in
several fields of computational molecular biology. Although this problem has
been extensively studied, it is still computationally challenging due to size
of the datasets that modern sequencing technologies can produce.

Results: We introduce Clark a novel approach to classify metagenomic reads at
the species or genus level with high accuracy and high speed. Extensive
experimental results on various metagenomic samples show that the
classification accuracy of Clark is better or comparable to the best state-of-
the-art tools and it is significantly faster than any of its competitors. In
its fastest single-threaded mode Clark classifies, with high accuracy, about
32 million metagenomic short reads per minute. Clark can also classify BAC
clones or transcripts to chromosome arms and centromeric regions.

Conclusions: Clark is a versatile, fast and accurate sequence classification
method, especially useful for metagenomics and genomics applications. It is
freely available at http://clark.cs.ucr.edu/.

