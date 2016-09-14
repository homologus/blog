---
title: A Neat Paper on FM-index
tags: []
categories:
- blog
---
Szymon Grabowski and colleagues, who [had been previously having a ball with
minimizers](http://www.homolog.us/blogs/blog/2014/07/11/minimizer-revolution-
continues-with-kmc-2-k-mer-counter/), submitted a neat paper on FM-index that
the readers may enjoy. Their code is available from [this
website](http://ranisz.iis.p.lodz.pl/indexes/fm/).
<!--more-->

[FM-index for dummies](http://arxiv.org/abs/1506.04896)

> The FM-index is a celebrated compressed data structure for full-text pattern
searching. After the first wave of interest in its theoretical developments,
we can observe a surge of interest in practical FM-index variants in the last
few years. These enhancements are often related to a bit-vector
representation, augmented with an efficient rank-handling data structure. In
this work, we propose a new, cache-friendly, implementation of the rank
primitive and advocate for a very simple architecture of the FM-index, which
trades compression ratio for speed. Experimental results show that our
variants are 2--3 times faster than the fastest known ones, for the price of
using typically 1.5--5 times more space.

