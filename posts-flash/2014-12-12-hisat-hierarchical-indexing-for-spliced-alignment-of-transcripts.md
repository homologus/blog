---
title: 'HISAT: Hierarchical Indexing for Spliced Alignment of Transcripts'
categories:
- rnaseq
---
[Link](http://biorxiv.org/content/early/2014/12/12/012591)
<!--more-->

> HISAT is a new, highly efficient system for alignment of sequences from RNA
sequencing experiments that achieves dramatically faster performance than
previous methods. HISAT uses a new indexing scheme, hierarchical indexing,
which is based on the Burrows-Wheeler transform and the Ferragina-Manzini (FM)
index. Hierarchical indexing employs two types of indexes for alignment: (1) a
whole-genome FM index to anchor each alignment, and (2) numerous local FM
indexes for very rapid extensions of these alignments. HISATs hierarchical
index for the human genome contains 48,000 local FM indexes, each representing
a genomic region of ~64,000 bp. The algorithm includes several customized
alignment strategies specifically designed for mapping RNA-seq reads across
multiple exons. In tests on a variety of real and simulated data sets, we show
that HISAT is the fastest system currently available, approximately 50 times
faster than TopHat2 and 12 times faster than GSNAP, with equal or better
accuracy than any other method. Despite its very large number of indexes,
HISAT requires only 4.3 Gigabytes of memory to align reads to the human
genome. HISAT supports genomes of any size, including those larger than 4
billion bases. HISAT is available as free, open-source software from
http://www.ccb.jhu.edu/software/hisat.

