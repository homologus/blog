---
title: Trinity Run Completed. Is This Typical?
tags: []
categories:
- rnaseq
---
Few days back, [we wrote](http://www.homolog.us/blogs/2012/09/26/an-
experience-with-new-trinity/) about Trinity assembly run of a RNAseq library.
The library has (21M x 2) PE reads, and each read is 101 nucleotides long. It
is a smaller version of much larger Illumina HiSeq library with reduction
being done through digital normalization.
<!--more-->

Trinity was started on Sept 24th 3AM in a server with 512G RAM and 32 cores,
and it completed on Oct 1st, 11AM.

Are we doing something wrong, or does your Trinity run take about the same
time on similar sized libraries?

An update: I ran Bowtie to map reads being assembled on to the assembled
transcriptome.

`

% bowtie -a Trinity.fasta-bt reads1.fq

# reads processed: 21217616

# reads with at least one reported alignment: 2161522 (10.19%)

# reads that failed to align: 19056094 (89.81%)

Reported 4725653 alignments to 1 output stream(s)

% bowtie -a Trinity.fasta-bt reads2.fq

# reads processed: 21217616

# reads with at least one reported alignment: 2161672 (10.19%)

# reads that failed to align: 19055944 (89.81%)

Reported 4726101 alignments to 1 output stream(s)`

