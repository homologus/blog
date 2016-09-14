---
title: LSC, an Alternative to PacBioToCA for Error-correction of PacBio Reads
tags: []
categories:
- blog
---
![Capture](http://www.homolog.us/blogs/wp-content/uploads/2013/02/Capture-
150x108.png)
<!--more-->

We got a heads up from
[@ErichMSchwarz](http://www.pnas.org/content/early/2012/09/17/1203045109)
about [LSC, which is a recently published new
algorithm](http://www.stanford.edu/~kinfai/LSC/LSC.pdf) for correcting Pacbio
reads from Illumina.

**Improving PacBio Long Read Accuracy by Short Read Alignment**

Kin Fai Au, Jason G. Underwood, Lawrence Lee, Wing Hung Wong

> The recent development of third generation sequencing (TGS) generates much
longer reads than second generation sequencing (SGS) and thus provides a
chance to solve problems that are difficult to study through SGS alone.
However, higher raw read error rates are an intrinsic drawback in most TGS
technologies. Here we present a computational method, LSC, to perform error
correction of TGS long reads (LR) by SGS short reads (SR). Aiming to reduce
the error rate in homopolymer runs in the main TGS platform, the PacBioH RS,
LSC applies a homopolymer compression (HC) transformation strategy to increase
the sensitivity of SR-LR alignment without scarifying alignment accuracy. We
applied LSC to 100,000 PacBio long reads from human brain cerebellum RNA-seq
data and 64 million single-end 75 bp reads from human brain RNA-seq data. The
results show LSC can correct PacBio long reads to reduce the error rate by
more than 3 folds. The improved accuracy greatly benefits many downstream
analyses, such as directional gene isoform detection in RNA-seq study.
Compared with another hybrid correction tool, LSC can achieve over double the
sensitivity and similar specificity.

You can find LSC-related thread in [seqanswers forum
here](http://seqanswers.com/forums/showthread.php?t=22099).

Following paragraph from LSC paper could be helpful for readers:

> **Comparison of LSC and PacBioToCA**

We are aware of only one alternative program for the combined

analysis of LR and SR data. The program PacBioToCA [11] also

makes use of information in SR to correct errors in LR. We

compared the performance of LSC with PacBioToCA (the latest

version on March 13, 2012) on the same LR and SR data sets.

PacBioToCA output 13,995 ecLRs, 13,980 (99.89%) of which are

longer than 460 bp. Comparing with PacBioToCA, LSC has

significantly higher sensitivity as it output a several-fold higher

number of ecLRs in every bin of read length (Figure 5).

We divided the 62,465 LSC ecLRs with sequence identities

higher or equal to 0.9 into 3 groups according to their sequence

identify and read length (L) (Figure 6). Group 1 (I= 0.9665 and

L = 917 bp at average) has 13,995 ecLRs, which is essentially

equivalent to the reads output from PacBioToCA (Table 3).

Group 2 (I= 0.9246 and L= 929 bp at average) has slightly lower

identity but may still be of high quality and should not be

discarded. In order to compare the qualities of Group1 and Group

2, we aligned both groups to the transcriptome and the genome by

BLAT and counted how many known exon junctions can be

detected respectively. From two alignments (against transcriptome

and genome) of each read, the one with more known junction

detections were counted. About the same numbers of true splices

were detected from Group 1 and Group 2 at every bin (Table 4).

Given that the two groups are similar in size, this comparison

indicates that the detection from Group 2 should be of similar

reliability to that from Group 1. By providing this large group of

additional ecLRs, LSC has extracted a larger amount of useful

information to us from the same data.

With an eight-core server (Intel(R) Xeon(R) CPUs, 2.66 GHz)

with 32 G memory, LSC finished the computation within 10

hours and used about 20 G disk space to store temporary files.

With the same machine, PacBioToCA took 81 hours of

computation time and required a much higher amount of disk

space (800,1,000 G) for temporary files. Thus, LSC is considerably

more efficient computationally. The online introduction of

PacBioToCA shows that it is developed originally for the assembly

of small genomes such as E. coli. It is perhaps not surprising that it

is not competitive with LSC in the analysis of reads from the

mammalian transcriptome, a task that LSC was specifically

optimized for handling.

