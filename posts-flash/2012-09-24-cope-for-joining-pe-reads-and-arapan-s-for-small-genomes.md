---
title: COPE (for Joining PE Reads) and Arapan-S (for Small Genomes)
tags: []
categories:
- blog
---
Two new papers may interest our readers. The first one from BGI will come out
in Bioinformatics and it joins PE reads before performing genome assembly
using de Bruijn assembler. The second one is on performing highly accurate
assembly of small genomes.
<!--more-->

Many groups are realizing that it is a waste to discard information provided
by paired end reads, and the solutions developed by them fall into two
tags: []
categories -

(a) some kind of pre-processing module to join those reads that can be joined
and continuing with the assembly,

(b) modification of de Bruijn graph formalism to incorporate pairing
information.

The first category is great, when it works. However, it may not be useful,
when the insert length large compared to read length.
[SPAdes](http://www.homolog.us/blogs/2012/09/17/few-thoughts-on-spades-
papers/) (and possibly Monument assembler of Rayan Chikhi) fall into the
second category, whereas FLASH, COPE and [a poster mentioned here
previously](http://www.homolog.us/blogs/2012/07/30/an-efficient-preprocessing-
module-for-joining-paired-end-reads-before-assembly/) use method in the first
category.

> **COPE: An accurate k-mer based pair-end reads connection tool

to facilitate genome assembly**

B. Liu et al.

Result: In this paper, we present an efficient tool called COPE (Connecting
Overlapped Pair-End reads), to connect overlapping pair-end reads using k-mer
frequencies. We evaluated our tool on 30x simulated pair-end reads from
Arabidopsis thaliana with 1% base error. COPE connected over 99% of reads with
98.8% accuracy, which is respectively 10% and 2% higher than the most recently
published tool FLASH. When COPE is applied to real reads for genome assembly,
the resulting contigs are found to have fewer errors and give a 14 fold
improvement in the N50 measurement when compared to the contigs produced using
unconnected reads.

Source code can be downloaded from [here](ftp://ftp.genomics.org.cn/pub/cope).

\--------------------

[Arapan-S](http://www.biomedcentral.com/1756-0500/5/243) comes from a Japanese
group and it claims to assemble very small genomes at great accuracy. We do
not know, where it stands compared to Ray.

> **Arapan-S: a fast and highly accurate whole-genome assembly software for
viruses and small genomes

**

Mohammed Sahli1* and Tetsuo Shibuya

**Conclusions**

Our findings show that the accuracy of the assembly was very high; the result
was checked against the European Bioinformatics Institute (EBI) database using
the NCBI BLAST Sequence Similarity Search. The identity and the genome
coverage was more than 99%. We also compared the efficiency of Arapan-S with
other well-known assemblers. In dealing with small genomes, the accuracy of
Arapan-S is significantly higher than the accuracy of other assemblers. The
assembly process is very fast and requires only a few seconds.

Project home page is [here](http://shibuyalab.hgc.jp/Arapan/).

