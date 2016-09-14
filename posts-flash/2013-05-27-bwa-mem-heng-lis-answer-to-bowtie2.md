---
title: BWA-MEM - Heng Li's Answer to Bowtie2
tags: []
categories:
- blog
---
BWA-MEM paper is now available from arxiv.
<!--more-->

[Aligning sequence reads, clone sequences and assembly contigs with BWA-
MEM](http://arxiv.org/pdf/1303.3997v1.pdf)

> BWA-MEM is a new alignment algorithm for aligning sequence reads or long
query sequences against a large reference genome such as human. It
automatically chooses between local and end-to-end alignments, supports
paired-end reads and performs split alignment. The algorithm is robust to
sequencing errors and applicable to a wide range of sequence lengths from 70bp
to a few megabases. For short-read mapping, BWA-MEM shows better performance
than several state-of-art read aligners to date. Availability and
implementation: BWA-MEM is implemented as a component of BWA, which is
available at [http://github.com/lh3/bwa](https://github.com/lh3/bwa).

It has nice comparison with other alignment algorithms.

> We evaluated the performance of BWA-MEM on simulated data together with
NovoAlign (http://novocraft.com), GEM, Bowtie2, Cushaw2, BWA-SW and BWA
(Figure 1). On accuracy, NovoAlign is the best. BWA-MEM is close to NovoAlign
for PE reads and is comparable to GEM and Cushaw2 for SE. On speed, BWA-MEM is
similar to GEM and Bowtie2 for this data set, but is about 6 times as fast as
Bowtie2 for a 650bp long-read data set.

