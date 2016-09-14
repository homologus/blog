---
title: Large-Scale Search of Transcriptomic Read Sets with Sequence Bloom Trees
categories:
- rnaseq
---
[Link](http://biorxiv.org/content/early/2015/03/26/017087)
<!--more-->

> Enormous databases of short-read RNA-seq sequencing experiments such as the
NIH Sequence Read Archive (SRA) are now available. However, these collections
remain difficult to use due to the inability to search for a particular
expressed sequence. A natural question is which of these experiments contain
sequences that indicate the expression of a particular sequence such as a gene
isoform, lncRNA, or uORF. However, at present this is a computationally
demanding question at the scale of these databases. We introduce an indexing
scheme, the Sequence Bloom Tree (SBT), to support sequence-based querying of
terabase-scale collections of thousands of short-read sequencing experiments.
We apply SBT to the problem of finding conditions under which query
transcripts are expressed. Our experiments are conducted on a set of 2652
publicly available RNA-seq experiments contained in the NIH for the breast,
blood, and brain tissues, comprising 5 terabytes of sequence. SBTs of this
size can be queried for a 1000 nt sequence in 19 minutes using less than 300
MB of RAM, over 100 times faster than standard usage of SRA-BLAST and 119
times faster than STAR. SBTs allow for fast identification of experiments with
expressed novel isoforms, even if these isoforms were unknown at the time the
SBT was built. We also provide some theoretical guidance about appropriate
parameter selection in SBT and propose a sampling-based scheme for potentially
scaling SBT to even larger collections of files. While SBT can handle any set
of reads, we demonstrate the effectiveness of SBT by searching a large
collection of blood, brain, and breast RNA-seq files for all 214,293 known
human transcripts to identify tissue-specific transcripts. The implementation
used in the experiments below is in C++ and is available as open source at
http://www.cs.cmu.edu/~ckingsf/software/bloomtree.

