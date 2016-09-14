---
title: High-throughput Microbial Population Genomics using the Cortex Variation Assembler
tags: []
categories:
- blog
---
Zamin Iqbal, who has been doing fascinating work with development of [Cortex
genome assembler](http://cortexassembler.sourceforge.net/), sent us an update
with [link to his latest paper published in Bioinformatics](http://bioinformat
ics.oxfordjournals.org/content/early/2012/11/19/bioinformatics.bts673.full.pdf
+html). Here is the abstract.
<!--more-->

> We have developed a software package, Cortex, designed for the analysis of
genetic variation by de novo assembly of multiple samples. This allows direct
comparison of samples without using a reference genome as intermediate, and
incorporates discovery and genotyping of SNPs, indels and larger events in a
single framework. We introduce pipelines which simplify the analysis of
microbial samples and increase discovery power; these also enable the
construction of a graph of known sequence and variation in a species, against
which new samples can be compared rapidly. We demonstrate the ease-of-use and
power by reproducing the results of studies using both long and short reads.

Cortex is an unusual genome assembler. Almost all other assemblers (no matter
whether de Bruijn graph-based, or non de Bruijn graph-based) start with the
assumption that two pairs of diploid chromosomes are identical. That is a
pretty good assumption except where it does not work :). Recently there is lot
of interest in finding information about phasing and genomic variation among a
large population. Aligning reads back to reference genome is the most used
strategy to identify SNPs, but insertion-deletions are harder to find with
typical alignment methods. Alignment strategy has a strong bias toward finding
what one already knows, i.e. the reference genome.

Based on comments from others in Twitterosphere and elsewhere, Cortex is very
good program not only for the originality of its algorithm ('colored' de
Bruijn graph), but also because it is light-weight and scalable. We expect to
go through the code and algorithm in the coming months, but for the time
being, we have to leave you with Zamin's email comment.

> We have a new paper showing we can distinguish 2 strains of MRSA in 3
minutes and 160Mb of RAM, and get as good results as a PNAS publication that
did whole genome assemblies and alignment. That was with Sanger reads, which
is kind of surprising that with long reads a de Bruijn approach can do
comparably well as a finished WG consensus assembly + alignment. Then we take
72 strains of S. aureus (100x 100bp illumina reads for each one) from another
paper, and again reproduce their results (10Gb RAM, 5 hours serially, I forget
how long if in parallel).

The goal was

1\. to show that you can go from reads to variants very quickly now.

2\. it provides a new way to compare a new sample with all known previous
samples, by comparing with the graph of all previous samples

