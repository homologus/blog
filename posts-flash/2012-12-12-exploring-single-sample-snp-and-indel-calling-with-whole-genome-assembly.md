---
title: Exploring Single-sample SNP and indel Calling with Whole-Genome Assembly
tags: []
categories:
- blog
---
Heng Li, who moved to Broad Institute, [posted an interesting article at
arxiv](http://arxiv.org/pdf/1203.6364v2.pdf) on a genome assembler that
combines both assembly and variant calling. We have not finished reading it,
but it is the most important paper for us to read today. (Note: The article is
already [ published in Bioinformatics](http://bioinformatics.oxfordjournals.or
g/content/early/2012/05/07/bioinformatics.bts280.abstract) journal. Thanks to
Nick Loman for pointing out.)
<!--more-->

> To explore the feasibility of using de novo assembly in the context of
resequencing, we developed a de novo assembler, fermi, that assembles Illumina
short reads into unitigs while preserving most of information of the input
reads. SNPs and INDELs can be called by mapping the unitigs against a
reference genome. By applying the method on 35-fold human resequencing data,
we showed that in comparison to the standard pipeline, our approach yields
similar accuracy for SNP calling and better results for INDEL calling. It has
higher sensitivity than other de novo assembly based methods for variant
calling. Our work suggests that variant calling with de novo assembly can be a
beneficial complement to the standard variant calling pipeline for whole-
genome resequencing. In the methodological aspects, we proposed FMD-index for
forward-backward extension of DNA sequences, a fast algorithm for finding all

super-maximal exact matches and one-pass construction of unitigs from an FMD-
index.

In this context, we would also encourage the readers to check [Cortex
assembler](http://cortexassembler.sourceforge.net/) from [Zamin Iqbal in
UK](http://cortexassembler.sourceforge.net/about_us.html).

> Cortex is an efficient and low-memory software framework for analysis of
genomes using sequence data. There are two main executables, being developed
in parallel streams: cortex_con (primary contact Mario Caccamo) is for
consensus genome assembly, and cortex_var (primary contact Zamin Iqbal) is for
variation and population assembly.

For a slightly different approach to derive variants from short reads, also
check [HapCompass algorithm](http://www.homolog.us/blogs/2012/08/28
/hapcompass-an-elegant-use-of-graphs-for-haplotype-assemblyphasing/).

