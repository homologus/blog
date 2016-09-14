---
title: 'FermiKit: assembly-based variant calling for Illumina resequencing data'
tags: []
categories:
- blog
---
[From Heng Li](http://arxiv.org/abs/1504.06574)
<!--more-->

> Summary: FermiKit is a variant calling pipeline for Illumina data. It de
novo assembles short reads and then maps the assembly against a reference
genome to call SNPs, short insertions/deletions (INDELs) and structural
variations (SVs). FermiKit takes about one day to assemble 30-fold human
whole-genome data on a modern 16-core server with 85GB RAM at the peak, and
calls variants in half an hour to an accuracy comparable to the current
practice. FermiKit assembly is a reduced representation of raw data while
retaining most of the original information.

