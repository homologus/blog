---
title: Basic Local Alignment with Successive Refinement (BLASR) for PacBio
tags: []
categories:
- blog
---
PacBio reads are long, but highly error-prone. Moreover, errors spread nearly
uniformly over the entire reads. BLASR is an alignment tool designed to align
such reads to error-free sequences. Researchers working on PacBio reads could
[access the software from
github](https://github.com/PacificBiosciences/blasr), but little information
was available on the algorithm.
<!--more-->

BLASR paper is out now for those few curious about the algorithm. Be ready
with your differential calculus book.

[Mapping single molecule sequencing reads using Basic Local Alignment with
Successive Refinement (BLASR): Theory and Application

Mark J Chaisson and Glenn Tesler

>

We describe the method BLASR (Basic Local Alignment with Successive
Refinement) for mapping Single Molecule Sequencing (SMS) reads that are
thousands to tens of thousands of bases long with divergence between the read
and genome dominated by insertion and deletion error. We also present a
combinatorial model of sequencing error that motivates why our approach is
effective. The results indicate that mapping SMS reads is both highly specific
and rapid.

\--------------

**Installation**: 

Installing BLASR is easy, but make sure you install [dynamic hdf5
libraries](http://www.hdfgroup.org/HDF5/release/obtain5.html#obtain) first.

**Running BLASR:**

(contributed by Jason Chin)

>

here is how I use the blasr to align PacBio reads to the contigs
(target.fasta). The "target.fasta.sa" is the suffix array from "target.fasta"
generated by sawriter.

blasr query.fa ./target.fasta -sa ./target.fasta.sa -bestn 40 -maxScore -500
-m 4 -nproc 24 -out target.m4 -maxLCPLength 15

the output format option "-m 4" generate the alignment coordinate. Not fully
documented, but I can explain that to you. (Easier in a phone...)

I use a 24 cores / 48G ram server for the alignment. It took about 2 to 3
hours aligning 3G PacBio Reads to 10^6 sequences of short read contigs with a
mean 3.5kbp length.
