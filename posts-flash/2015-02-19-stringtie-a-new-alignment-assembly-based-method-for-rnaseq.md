---
title: StringTie - A New Alignment + Assembly Based Method for RNAseq
categories:
- rnaseq
---
[This
paper](http://www.nature.com/nbt/journal/vaop/ncurrent/full/nbt.3122.html) is
from Salzberg group, who developed Bowtie/Tophat.
<!--more-->

> Methods used to sequence the transcriptome often produce more than 200
million short sequences. We introduce StringTie, a computational method that
applies a network flow algorithm originally developed in optimization theory,
together with optional de novo assembly, to assemble these complex data sets
into transcripts. When used to analyze both simulated and real data sets,
StringTie produces more complete and accurate reconstructions of genes and
better estimates of expression levels, compared with other leading transcript
assembly programs including Cufflinks, IsoLasso, Scripture and Traph. For
example, on 90 million reads from human blood, StringTie correctly assembled
10,990 transcripts, whereas the next best assembly was of 7,187 transcripts by
Cufflinks, which is a 53% increase in transcripts assembled. On a simulated
data set, StringTie correctly assembled 7,559 transcripts, which is 20% more
than the 6,310 assembled by Cufflinks. As well as producing a more complete
transcriptome assembly, StringTie runs faster on all data sets tested to date
compared with other assembly software, including Cufflinks.

![](http://www.nature.com/nbt/journal/vaop/ncurrent/carousel/nbt.3122-F1.jpg)

