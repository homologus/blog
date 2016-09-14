---
title: Another PacBio Development - Adam Phillippy's New MHAP Module
tags: []
categories:
- blog
---
Alignment speed is the biggest bottleneck in PacBio assembly. Therefore, those
working on PacBio reads will find [the following release](http://wgs-
assembler.sourceforge.net/wiki/index.php?title=PBcR) helpful.
<!--more-->

> June 14, 2014 - PBcR and CA 8.2 alpha as source or pre-compiled for Linux is
now available. PBcR now incorporates a novel probabilistic overlapper for
self-correction of sequences named MHAP. This allows assembly of prokaryotic
genomes in < 30 minutes on a typical desktop and assembly of small eukaryotic
genomes in < 2 days. If you use MHAP, please cite the Biology of Genomes
poster (Berlin K., Koren, S. et. al. Reducing assembly complexity of genomes
with single-molecule sequencing. Biology of Genomes, 2014). For best results,
java 1.7r51 or newer is recommended to use MHAP.

How good is it? Here is the plain language description -

![Capture](http://www.homolog.us/blogs/wp-
content/uploads/2014/06/Capture6-300x97.png)

\----------------------------------------------

Given that alignment is a big bottleneck, we previously checked whether BWA-
mem could improve the execution time. Heng Li came up with a set of optimal
parameters to get the best alignment. Readers may find [the following comment
from Irek](http://www.homolog.us/blogs/blog/2014/04/07/bwa-mem-vs-blasr-for-
pacbio-need-help-with-benchmarking/) in that thread helpful -

> Hey, I just finished comparison for new PacBio RSII data (CCS and CLR),
used: bwa-sw,mem,blasr,ssaha2,smalt,last and agile.

Checked speed, memory, mapping status of reads, then went for precision-recall
assessment, and finished with the analysis of error model recognition.

Actually new version of SMALT looks like a winner and its really fast and
memory efficient.

As for mem blasr. For CCS they are comparable in terms of precision-recall,
but for CLR, mem definitely looses.

