---
title: Ultrafast SNP Analysis using the Burrows-Wheeler Transform of Short-read Data
tags: []
categories:
- blog
---
[This recent paper](http://bioinformatics.oxfordjournals.org/content/early/201
5/01/19/bioinformatics.btv024.short) appears quite interesting (h/t: Ruibang).
It starts with the BWT of short read library (e.g. BCR), and skips the
alignment step altogether to go straight to SNP determination.
<!--more-->

> Motivation: Sequence-variation analysis is conventionally performed on
mapping results that are highly redundant and occasionally contain undesirable
heuristic biases. A straightforward approach to SNP analysis, using the
Burrows-Wheeler transform (BWT) of short-read data, is proposed.

Results: The BWT makes it possible to simultaneously process collections of
read fragments of the same sequences; accordingly,SNPs were found from the BWT
much faster than from the mapping results. It took only a few minutes to find
SNPs from the BWT (with supplementary data, FDC) using a desktop workstation
in the case of human exome or transcriptome sequencing data and twenty minutes
using a dual-CPU server in the case of human genome sequencing data. The SNPs
found with the proposed method almost agreed with those found by a time-
consuming state-of-the-art tool, except for the cases in which the use of
fragments of reads led to sensitivity loss or sequencing depth was not
sufficient. These exceptions were predictable in advance on the basis of
minimum length for uniqueness (MLU) and fragment depth of coverage (FDC)
defined on the reference genome. Moreover, BWT and FDC were computed in less
time than it took to get the mapping results, provided that the data was large
enough.

Availability: A proof-of-concept binary code for a Linux platform is available
on request to the corresponding author.

Contact: kouichi.kimura.hh@hitachi.com

\---------------------------------------

The authors are not new to using BWT and suffix arrays for analyzing genomic
data. Here are a few of their previous papers -

2009 -

[Computation of Rank and Select Functions on Hierarchical Binary String and
Its Application to Genome Mapping Problems for Short-Read DNA
Sequences](http://online.liebertpub.com/doi/abs/10.1089/cmb.2008.0146)

2009 -

[Localized suffix array and its application to genome mapping problems for
paired-end short reads](http://www.ncbi.nlm.nih.gov/pubmed/20180262)

2011 -

[Seed-set construction by equi-entropy partitioning for efficient and
sensitive short-read mapping](http://dl.acm.org/citation.cfm?id=2039959)

