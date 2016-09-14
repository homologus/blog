---
title: 'BARCODE: Fast Lossless Compression via Cascading Bloom Filters'
tags: []
categories:
- blog
---
This is a RECOMB poster of very nice work done by Roye Rozov -
<!--more-->

[http://www.homolog.us/blogs/wp-content/uploads/2014/05/ccc2.png](http://cdn.f
1000.com/posters/docs/261444883)">![ccc](http://www.homolog.us/blogs/wp-
content/uploads/2014/05/ccc2-300x170.png)

> Background / Purpose:

Reference-based compression is currently the most efficient means of
compressing deep sequencing read sequences. The most time-consuming step of
performing such compression is the alignment of reads to a reference genome.

Main conclusion:

We developed an algorithm which allows for fast reference-based compression by
hashing read sequences into bloom filters. We observed that by avoiding
alignment to the reference genome, we can compress nearly as well as
alignment-based methods up to an order of magnitude (9x) faster.

