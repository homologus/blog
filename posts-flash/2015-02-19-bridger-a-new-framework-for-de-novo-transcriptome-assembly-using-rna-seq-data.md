---
title: 'Bridger: a new framework for de novo transcriptome assembly using RNA-seq
  data'
categories:
- rnaseq
---
[Link](http://genomebiology.com/2015/16/1/30/abstract)
<!--more-->

The main idea is here.

> As of now, all the existing de novo assemblers use a de Bruijn graph to
represent the assembly problem, which processes each sequence into a set of
overlapping substrings of length k bps, called k-mers, where k is a parameter,
and recover the splicing isoforms from the graph [23]. Generally speaking,
larger k values tend to perform better on transcripts with high gene-
expression levels or longer contigs, while smaller k values perform better on

transcripts with low gene-expression levels or shorter contigs. It seems
unlikely that a single k value will yield an optimal overall assembly. Hence
some assemblers, such as Trans- ABySS [23], Oases-M [21] (multiple-k version
of Oases) and IDBA-Tran [24], use a multiple-k strategy, in which multiple
assemblies using different k values are merged to get a higher sensitivity,
but at the cost of introducing more false-positive transcripts.

In this paper, we present a new assembler, Bridger, aiming to build a bridge
between the key ideas of two popular assemblers, the reference-based assembler
Cufflinks [12] and de novo assembler Trinity [11]. Specifically, we have
generalized the main techniques employed by Cufflinks to overcome the
limitations of Trinity, hence to develop a more general de novo assembler
better than the state of the art. We have tested Bridger on two standard RNA-
seq datasets, one dog and one human dataset, and on one strand-specific mouse
RNA-seq data. In each case, Bridger assembled more reference transcripts than
the other de novo assemblers, while reporting 10,000 to 30,000 fewer candidate
transcripts, which greatly reduced the false positive assemblies. In addition,
Bridger runs much faster and requires less memory space than most of compared
methods, and exhibits competitive CPU time. The performance of Bridger is even
comparable with the reference-based assembler Cufflinks in both sensitivity
and accuracy. In addition, a multiple-k version of Bridger, Bridger-M, can
further improve the assembly sensitivity by merging assemblies from different
k values.

