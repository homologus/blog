---
title: 'QuorUM: An Error Corrector for Illumina Reads'
tags: []
categories:
- blog
---
[This new paper](http://www.ncbi.nlm.nih.gov/pubmed/26083032) comes from G.
Marais, Alex Zimin and [Jim Yorke of minimizer
fame](http://www.homolog.us/blogs/blog/2014/04/06/2014-the-year-of-minimizers-
in-bioinformatics/).
<!--more-->

> MOTIVATION:

Illumina Sequencing data can provide high coverage of a genome by relatively
short (most often 100 bp to 150 bp) reads at a low cost. Even with low
(advertised 1%) error rate, 100 coverage Illumina data on average has an error
in some read at every base in the genome. These errors make handling the data
more complicated because they result in a large number of low-count erroneous
k-mers in the reads. However, there is enough information in the reads to
correct most of the sequencing errors, thus making subsequent use of the data
(e.g. for mapping or assembly) easier. Here we use the term "error correction"
to denote the reduction in errors due to both changes in individual bases and
trimming of unusable sequence. We developed an error correction software
called QuorUM. QuorUM is mainly aimed at error correcting Illumina reads for
subsequent assembly. It is designed around the novel idea of minimizing the
number of distinct erroneous k-mers in the output reads and preserving the
most true k-mers, and we introduce a composite statistic ? that measures how
successful we are at achieving this dual goal. We evaluate the performance of
QuorUM by correcting actual Illumina reads from genomes for which a reference
assembly is available.

RESULTS:

We produce trimmed and error-corrected reads that result in assemblies with
longer contigs and fewer errors. We compared QuorUM against several published
error correctors and found that it is the best performer in most metrics we
use. QuorUM is efficiently implemented making use of current multi-core
computing architectures and it is suitable for large data sets (1 billion
bases checked and corrected per day per core). We also demonstrate that a
third-party assembler (SOAPdenovo) benefits significantly from using QuorUM
error-corrected reads. QuorUM error corrected reads result in a factor of 1.1
to 4 improvement in N50 contig size compared to using the original reads with
SOAPdenovo for the data sets investigated.

AVAILABILITY:

QuorUM is distributed as an independent software package and as a module of
the MaSuRCA assembly software. Both are available under the GPL open source
license at http://www.genome.umd.edu.

Readers may also take a look at [Heng Li's error correction
program](http://www.homolog.us/blogs/blog/2015/02/18/a-sequel-to-heng-lis-
mysterious-new-program/) <del>published</del> preprinted early this year.

