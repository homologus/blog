---
title: Israeli Paper on Efficient Pre-processing of PE Reads is Now Published
tags: []
categories:
- blog
---
About a year back, we covered an NGS-related poster from an Israeli group -
<!--more-->

[An Efficient Preprocessing Module for Joining Paired end Reads before
Assembly](http://www.homolog.us/blogs/2012/07/30/an-efficient-preprocessing-
module-for-joining-paired-end-reads-before-assembly/)

@genetics_blog reported about a Bioinformatics paper from the authors that
could be related to the poster. Unfortunately, the Bioinformatics paper is
locked for a year or so. So, we will update here in April 2014, whether the
paper is indeed the same as the poster. In the meanwhile, enjoy the abstract,
which is open access.

[ELOPER: elongation of paired-end reads as a pre-processing tool for improved
de novo genome assembly](http://bioinformatics.oxfordjournals.org/content/earl
y/2013/04/29/bioinformatics.btt169.short?rss=1&utm_source=feedly)

> Motivation: Paired-end sequencing resulting in gapped short reads is
commonly used for de novo genome assembly. Assembly methods use paired-end
sequences in a two-step process, first treating each read-end independently,
only later invoking the pairing to join the contiguous assemblies (contigs)
into gapped scaffolds. Here, we present ELOPER, a pre-processing tool for
pair-end sequences that produces a better read library for assembly programs.

Results: ELOPER proceeds by simultaneously considering both ends of paired
reads generating elongated reads. We show that ELOPER theoretically doubles
read-lengths while halving the number of reads. We provide evidence that pre-
processing read libraries using ELOPER leads to considerably improved
assemblies as predicted from the LanderWaterman model.

Availability: http://sourceforge.net/projects/eloper.

Speaking of ways to join PE reads, BGI also published on the same topic few
months back. You will find the link in this blog post.

[COPE (for Joining PE Reads) and Arapan-S (for Small
Genomes)](http://www.homolog.us/blogs/2012/09/24/cope-for-joining-pe-reads-
and-arapan-s-for-small-genomes/)

