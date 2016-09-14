---
title: Accurate selfcorrection of errors in long reads using de Bruijn graphs
tags: []
categories:
- blog
---
[Link](http://arxiv.org/abs/1604.02233)
<!--more-->

> New long read sequencing technologies, like PacBio SMRT and Oxford NanoPore,
can produce sequencing reads up to 50,000 bp long but with an error rate of at
least 15%. Reducing the error rate is necessary for subsequent utilisation of
the reads in, e.g., de novo genome assembly. The error correction problem has
been tackled either by aligning the long reads against each other or by a
hybrid approach that uses the more accurate short reads produced by second
generation sequencing technologies to correct the long reads. We present an
error correction method that uses long reads only. The method consists of two
phases: first we use an iterative alignment-free correction method based on de
Bruijn graphs with increasing length of k-mers, and second, the corrected
reads are further polished using long-distance dependencies that are found
using multiple alignments. According to our experiments the proposed method is
the most accurate one relying on long reads only for read sets with high
coverage. Furthermore, when the coverage of the read set is at least 75x, the
throughput of the new method is at least 20% higher. LoRMA is freely available
at this http.

