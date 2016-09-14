---
title: RapMap - Today's Must Read Paper
categories:
- rnaseq
---
Rob Patro, the senior author of the paper, also developed
[Sailfish](http://www.homolog.us/blogs/rnaseq/2014/04/21/goodbye-rsem-
sailfish-paper-published/).
<!--more-->

[RapMap: A Rapid, Sensitive and Accurate Tool for Mapping RNA-seq Reads to
Transcriptomes](http://biorxiv.org/content/early/2016/01/16/029652)

> Motivation: The alignment of sequencing reads to a transcriptome is a common
and important step in many RNA-seq analysis tasks. When aligning RNA-seq reads
directly to a transcriptome (as is common in the de novo setting or when a
trusted reference annotation is available), care must be taken to report the
potentially large number of multi-mapping locations per read. This can pose a
substantial computational burden for existing aligners, and can considerably
slow downstream analysis.

Results: We introduce a novel concept, quasi-mapping, and an efficient
algorithm implementing this approach for mapping sequencing reads to a
transcriptome. By attempting only to report the potential loci of origin of a
sequencing read, and not the base-to-base alignment by which it derives from
the reference, RapMap --- our tool implementing quasi-mapping --- is capable
of mapping sequencing reads to a target transcriptome substantially faster
than existing alignment tools. The algorithm we employ to implement quasi-
mapping uses several efficient data structures and takes advantage of the
special structure of shared sequence prevalent in transcriptomes to rapidly
provide highly-accurate mapping information. We demonstrate how quasi-mapping
can be successfully applied to the problems of transcript-level quantification
from RNA-seq reads and the clustering of contigs from de novo assembled
transcriptomes into biologically-meaningful groups.

Availability: RapMap is implemented in C++11 and is available as open-source
software, under GPL v3, at https://github.com/COMBINE-lab/RapMap.

