---
title: 'Boiler: Lossy compression of RNA-seq alignments using coverage vectors'
tags: []
categories:
- blog
---
[Link](http://biorxiv.org/content/early/2016/02/22/040634)
<!--more-->

> We describe Boiler, a new software tool for compressing and querying large
collections of RNA-seq alignments. Boiler discards most per-read data, keeping
only a genomic coverage vector plus a few empirical distributions summarizing
the alignments. Since most per-read data is discarded, storage footprint is
often much smaller than that achieved by other compression tools. Despite
this, the most relevant per-read data can be recovered; we show that Boiler
compression has only a slight negative impact on results given by downstream
tools for isoform assembly and quantitation. Boiler also allows the user to
pose fast and useful related queries without decompressing the entire file.
Boiler is free open source software available from github.com/jpritt/boiler.

