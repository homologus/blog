---
title: Minimap and Miniasm Paper is out
tags: []
categories:
- blog
---
Our readers [learned many months
back](http://www.homolog.us/blogs/blog/2015/09/30/minimap-a-minimizer-based-
mapping-program/) about the amazing programs for pacbio assembly from Heng Li.
For others -
<!--more-->

[Minimap and miniasm: fast mapping and de novo assembly for noisy long sequenc
es](http://bioinformatics.oxfordjournals.org/content/early/2016/03/18/bioinfor
matics.btw152.short?rss=1)

> Motivation: Single Molecule Real-Time (SMRT) sequencing technology and
Oxford Nanopore technologies (ONT) produce reads over 10kbp in length, which
have enabled high-quality genome assembly at an affordable cost. However, at
present, long reads have an error rate as high as 1015%. Complex and
computationally intensive pipelines are required to assemble such reads.

Results: We present a new mapper, minimap, and a de novo assembler, miniasm,
for efficiently mapping and assembling SMRT and ONT reads without an error
correction stage. They can often assemble a sequencing run of bacterial data
into a single contig in a few minutes, and assemble 45-fold C. elegans data in
9 minutes, orders of magnitude faster than the existing pipelines, though the
consensus sequence error rate is as high as raw reads. We also introduce a
pairwise read mapping format (PAF) and a graphical fragment assembly format
(GFA), and demonstrate the interoperability between ours and current tools.

Availability and implementation: https://github.com/lh3/minimap and
https://github.com/lh3/miniasm

