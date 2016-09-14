---
title: 'MetaFlow: Metagenomic profiling based on whole-genome coverage analysis with
  min-cost flows'
tags: []
categories:
- blog
---
A few years back, Veli Mkinen's group [proposed using min-flow for RNAseq
instead of expectation-maximization (EM)](http://bmcbioinformatics.biomedcentr
al.com/articles/10.1186/1471-2105-14-S5-S15). I suspect this new [new arxiv
paper](http://biorxiv.org/content/early/2016/01/29/038208) is related
algorithmically, but developed for a different context (metagenomics).
<!--more-->

> High-throughput sequencing (HTS) of metagenomes is proving essential in
understanding the environment and diseases. State-of-the-art methods for
discovering the species and their abundances in an HTS metagenomic sample are
based on genome-specific markers, which can lead to skewed results, especially
at species level. We present MetaFlow, the first method based on coverage
analysis across entire genomes that also scales to HTS samples. We formulated
this problem as an NP-hard matching problem in a bipartite graph, which we
solved in practice by min-cost flows. On synthetic data sets of varying
complexity and similarity, MetaFlow is more precise and sensitive than popular
tools such as MetaPhlAn, mOTU, GSMer and BLAST, and its abundance estimations
at species level are two to four times better in terms of L1-norm. On a real
human stool data set, MetaFlow identifies B.uniformis as most predominant, in
line with previous human gut studies, whereas marker-based methods report it
as rare. MetaFlow is freely available at http://cs.helsinki.fi/gsa/metaflow

