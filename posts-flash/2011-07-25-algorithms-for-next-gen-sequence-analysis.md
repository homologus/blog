---
title: Algorithms for Next-gen Sequence Analysis
tags:
- introductory
- bioinformatics
categories:
- blog
---
The field of next-gen sequence analysis is advancing so rapidly that new
algorithms come out almost every day. Here we provide a broad categorization
for such algorithms and describe critical challenges for each category. This
will help us understand the approaches presented in various algorithms, when
we look into each one in more detail.
<!--more-->

Usually a scientist submits DNA samples for an organism to a core facility for
sequencing and receives a large disk full of sequence data. The first
categorization comes from whether the organism has a reference sequence.
Second categorization comes from whether the sample is genomic or
transcriptomic.

As a 2x2 matrix, the categories are

**A.** Organism has reference genome and sample is genomic

**B.** Organism does not have reference genome and sample is genomic

**C.** Organism has reference genome and sample is transcriptomic

**D.** Organism does not have reference genome and sample is transcriptomic

**Challenges in Category A**

* Alignment of short reads on to reference genome.

* Identification of SNPs.

* Identification of insertion-deletions.

**Challenges in Category B**

* Genome assembly from short reads.

**Challenges in Category C**

* Alignment of transcriptomic reads on to reference genome.

* Expression profiling.

* Alternate splicing.

**Challenges in Category D**

* Transcriptome assembly (works differently from genome assembly).

* Expression profiling without reference genome.

* Alternate splicing.

We prefer this categorization, because each category presents its unique
challenges.

The primary focus of algorithms developed for category A is speed. Usually
millions, and sometimes billions, of reads need to be rapidly mapped on to
reference genome for further analysis. Any improvement in speed can make major
improvement in time for analysis.

The amount of computer memory (RAM) needed for assembly is the main concern of
category B algorithms. Conceptually, all reads need to be loaded on to memory
and compared before an assembly method joins them into large scaffolds.
Therefore, assembly of large genomes is memory intensive.

Category C has similarities with category A with added difficulty from intron-
exon junctions. Algorithms that map contiguous genomic reads do not handle
split junctions and alternate splicing properly.

Category D cannot directly use category B algorithms, because genome assembly
programs assume frequency uniformity of reads from all parts of genome. That
is a bad assumption fortranscriptomic reads, because expression levels of
different genes can vary wildly.

We will keep the above categories in mind in our future discussions on various
algorithms.

