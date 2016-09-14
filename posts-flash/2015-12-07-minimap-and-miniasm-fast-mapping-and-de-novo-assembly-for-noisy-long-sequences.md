---
title: 'Minimap and miniasm: fast mapping and de novo assembly for noisy long sequences'
tags: []
categories:
- blog
---
A few weeks back, we informed readers about Heng Li's new program ["Minimap A
Minimizer-based Mapping
Program"](http://www.homolog.us/blogs/blog/2015/09/30/minimap-a-minimizer-
based-mapping-program/). The paper is now available
[here](http://arxiv.org/abs/1512.01801).
<!--more-->

> Motivation: Single Molecule Real-Time (SMRT) sequencing technology and
Oxford Nanopore technologies (ONT) produce reads over 10kbp in length, which
have enabled high-quality genome assembly at an affordable cost. However, at
present, long reads have an error rate as high as 10-15%. Complex and
computationally intensive pipelines are required to assemble such reads.

Results: We present a new mapper, minimap, and a de novo assembler, miniasm,
for efficiently mapping and assembling SMRT and ONT reads without an error
correction stage. They can often assemble a sequencing run of bacterial data
into a single contig in a few minutes, and assemble 45-fold C. elegans data in
9 minutes, orders of magnitude faster than the existing pipelines. We also
introduce a pairwise read mapping format (PAF) and a graphical fragment
assembly format (GFA), and demonstrate the interoperability between ours and
current tools.

Availability and implementation: [this https
URL](https://github.com/lh3/minimap) and [this https
URL](https://github.com/lh3/miniasm)

