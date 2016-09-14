---
title: 'ScaffMatch: Scaffolding Algorithm Based on Maximum Weight Matching'
tags: []
categories:
- blog
---
A new scaffolding paper is published in
[Bioinformatics](http://www.ncbi.nlm.nih.gov/pubmed/25890305).
<!--more-->

> MOTIVATION:

Next-generation high-throughput sequencing (HTS) has become a state-of-the-art
technique in genome assembly. Scaffolding is one of the main stages of the
assembly pipeline. During this stage contigs assembled from the paired-end
reads are merged into bigger chains called scaffolds. Due to a high-level of
statistical noise, chimeric reads, genome repeats the problem of scaffolding
is a challenging task. Current scaffolding software packages widely vary in
their quality and are highly dependent on the read data quality and genome
complexity. There are no clear winners and multiple opportunities for further
improvements of the tools still exist.

RESULTS:

This paper presents an efficient scaffolding algorithm ScaffMatch that is able
to handle reads with both short (<600 bp) and long (>35000 bp) insert sizes
producing high-quality scaffolds. We evaluate our scaffolding tool with the
F-score and other metrics (N50, corrected N50) on 8 data sets comparing it
with the most available packages. Our experiments show that ScaffMatch is the
tool of preference for the most data sets.

AVAILABILITY:

The source code is available at
http://alan.cs.gsu.edu/NGS/?q=content/scaffmatch.

