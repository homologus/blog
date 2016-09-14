---
title: Alignment Papers We are Trying to Make Sense of
tags: []
categories:
- blog
---
[Albert Einstein](http://www.goodreads.com/quotes/19421-if-you-can-t-explain-
it-to-a-six-year-old) \-
<!--more-->

> If you can't explain it to a six year old, you don't understand it yourself.

Yesterday, we got hold of a six year old and explained how to do Burrows
Wheeler transform and reverse to him. He seemed to have enjoyed the new game.
Our next goal is to understand the algorithms of following four paper in a
satisfactory manner (as suggested by the above quote). The regular
commentaries will resume, only when (if) the experiment succeeds. So, please
wish us luck.

1\. Compressed Indexing and Local Alignment of DNA - T. W. Lam et al.
Bioinformatics (2008).

2\. High Throughput Short Read Alignment via Bi-directional BWT - T. W. Lam et
al. IEEE Bioinfo. (2009).

3\. [Exploring single-sample SNP and INDEL calling with whole-genome de novo
assembly - H. Li (2013).](http://arxiv.org/abs/1203.6364)

4\. [Aligning sequence reads, clone sequences and assembly contigs with BWA-
MEM. arXiv:1303.3997v1 - H. Li (2013).](http://arxiv.org/abs/1303.3997)

We are also going through Heng Li's BWA code, and especially two files
-'bwamem.c' written by him and 'bwt_gen.c' from Wong Chi Kwong.

[From the BWA manual](http://bio-bwa.sourceforge.net/bwa.shtml) \-

>

BWA is largely influenced by BWT-SW. It uses source codes from BWT-SW and
mimics its binary file formats; BWA-SW resembles BWT-SW in several ways. The
initial idea about BWT-based alignment also came from the group who developed
BWT-SW. At the same time, BWA is different enough from BWT-SW. The short-read
alignment algorithm bears no similarity to Smith-Waterman algorithm any more.
While BWA-SW learns from BWT-SW, it introduces heuristics that can hardly be
applied to the original algorithm. In all, BWA does not guarantee to find all
local hits as what BWT-SW is designed to do, but it is much faster than BWT-SW
on both short and long query sequences.

I started to write the first piece of codes on 24 May 2008 and got the initial
stable version on 02 June 2008. During this period, I was acquainted that
Professor Tak-Wah Lam, the first author of BWT-SW paper, was collaborating
with Beijing Genomics Institute on SOAP2, the successor to SOAP (Short
Oligonucleotide Analysis Package). SOAP2 has come out in November 2008.
According to the SourceForge download page, the third BWT-based short read
aligner, bowtie, was first released in August 2008. At the time of writing
this manual, at least three more BWT-based short-read aligners are being
implemented.

The BWA-SW algorithm is a new component of BWA. It was conceived in November
2008 and implemented ten months later.

The BWA-MEM algorithm is based on an algorithm finding super-maximal exact
matches (SMEMs), which was first published with the fermi assembler paper in
2012. I first implemented the basic SMEM algorithm in the fastmap command for
an experiment and then extended the basic algorithm and added the extension
part in Feburary 2013 to make BWA-MEM a fully featured mapper.

