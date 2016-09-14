---
title: Very Efficient Hybrid Assembler for PacBio Data
tags: []
categories:
- blog
---
Reader Chengxi Ye mentioned to us a few months back that he developed a very
efficient genome assembler for PacBio data, which did PacBio assembly of human
genome in 6 hours on a desktop computer compared to >400K CPU hours using a
cluster. For those, who do not know Chengxi Ye, he was the author of
[SparseAssembler](http://www.biomedcentral.com/1471-2105/13/S6/S1) and also
developed [ultrafast basecaller
BlindCall](http://www.homolog.us/blogs/blog/2014/01/23/blindcall-ultra-fast-
base-calling-algorithm-using-blind-deconvolution/). The algorithm of
SparseAssembler is more relevant in the current context, because he leveraged
its compression scheme in the new PacBio/hybrid assembler.
<!--more-->

The paper is posted in arxiv and the programs can be downloaded from
[here](https://sites.google.com/site/dbg2olc/).

[DBG2OLC: Efficient Assembly of Large Genomes Using the Compressed Overlap
Graph](http://arxiv.org/abs/1410.2801)

> The genome assembly computational problem is preventing the transition from
the prevalent second generation to third generation sequencing technology. The
problem emerged because the erroneous long reads made the assembly pipeline
prohibitive expensive in terms of computational time and memory space
consumption.

In this paper, we propose and demonstrate a novel algorithm that allows
efficient assembly of long erroneous reads of mammalian size genomes on a
desktop PC. Our algorithm converts the de novo genome assembly problem from
the de Bruijn graph to the overlap layout consensus framework. We only need to
focus on the overlaps composed of reads that are non-contained within any
contigs built with de Bruijn graph algorithm, rather than on all the overlaps
in the genome data sets. For each read spanning through several contigs, we
compress the regions that lie inside each de Bruijn graph contigs, which
greatly lowers the length of the reads and therefore the complexity of the
assembly problem. The new algorithm transforms previously prohibitive tasks
such as pair-wise alignment into jobs that can be completed within small
amount of time. A compressed overlap graph that preserves all necessary
information is constructed with the compressed reads to enable the final-stage
assembly.

We implement the new algorithm in a proof-of-concept software package DBG2OLC.
Experiments with the sequencing data from the third generation technologies
show that our method is able to assemble large genomes much more efficiently
than existing methods. On a large PacBio human genome dataset we calculated
the pair-wise alignment of 54x erroneous long reads of human genome in 6 hours
on a desktop computer compared to the 405,000 CPU hours using a clusters,
previously reported by Pacific Biosciences. The final assembly results were in
comparably high quality.

