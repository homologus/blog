---
title: 'LoRDEC: Accurate and Efficient Long Read Error Correction'
tags: []
categories:
- blog
---
Readers may recall [our post](http://www.homolog.us/blogs/blog/2014/07/16
/minias-new-home-gatb-genome-assembly-analysis-tool-box/) about Rayan Chikhi,
Guillaume Rizk, Dominique Lavenier and their collaborators converting their
efficient programs like Minia into an entire library with useful modules. Now
others are building on top of GATB and [LoRDEC is one success
story](http://atgc.lirmm.fr/lordec/). You can access the paper [at this
link](http://bioinformatics.oxfordjournals.org/content/30/24/3506) (h/t: E.
Rivals).
<!--more-->

> Motivation: PacBio single molecule real-time sequencing is a third-
generation sequencing technique producing long reads, with comparatively lower
throughput and higher error rate. Errors include numerous indels and
complicate downstream analysis like mapping or de novo assembly. A hybrid
strategy that takes advantage of the high accuracy of second-generation short
reads has been proposed for correcting long reads. Mapping of short reads on
long reads provides sufficient coverage to eliminate up to 99% of errors,
however, at the expense of prohibitive running times and considerable amounts
of disk and memory space.

Results: We present LoRDEC, a hybrid error correction method that builds a
succinct de Bruijn graph representing the short reads, and seeks a corrective
sequence for each erroneous region in the long reads by traversing chosen
paths in the graph. In comparison, LoRDEC is at least six times faster and
requires at least 93% less memory or disk space than available tools, while
achieving comparable accuracy.

Availability and implementaion: LoRDEC is written in C++, tested on Linux
platforms and freely available at http://atgc.lirmm.fr/lordec.

Readers may also find the following posts relevant.

[Very Efficient Hybrid Assembler for PacBio
Data](http://www.homolog.us/blogs/blog/2014/10/13/very-efficient-hybrid-
assembler-for-pacbio-data/)

[Cerulean: A Hybrid Assembly using High Throughput Short and Long
Reads](http://www.homolog.us/blogs/blog/2013/08/09/cerulean-a-hybrid-assembly-
using-high-throughput-short-and-long-reads/)

