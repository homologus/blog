---
title: Bi-directional BWT and 2BWT Alignment Algorithm
tags: []
categories:
- blog
---
It is an old paper from 2009 and most readers are probably familiar with it.
So, please excuse our ignorance.
<!--more-->

[High Throughput Short Read Alignment via Bi-directional
BWT](http://hub.hku.hk/bitstream/10722/129577/1/Content.pdf)

![](http://i.cs.hku.hk/~twlam/index_files/image002.jpg)

> The original BWT allows searching of a pattern in one direction, namely,
from right to left (backward search). However, for ef?cient approximate
pattern searching, we need a data structure that can support searching in both
directions (forward and backward search) and allow us to switch from forward
to backward search or vice versa in the course of aligning the pattern. This
would enable us to start matching a pattern from the middle, then extend the
search in either directions and switch directions in the alignment process. A
seemingly trivial solution is to keep two BWTs, one for the original sequence
and the other for the reversal. Then forward search can be done via a backward
search on the reversal of the pattern based on the latter BWT.

However, this solution cannot allow interleaving the backward and forward
search. And it deals with two separate searching space, demanding a lot more
memory (see Section III for details). We develop a new indexing data
structure, called bi-directional BWT, to solve this problem. Based on bi-
directional BWT, we develop a new short read alignment tool 2BWT, which is
faster than all existing tools.

Oddly, even though the above paper is old, not too many bioinformatics papers
outside T.W. Lam's group cite it. [Jared
Simpson](http://bioinformatics.oxfordjournals.org/content/26/12/i367.full) and
[Timo
Beller](http://www.sciencedirect.com/science/article/pii/S1570866712001104)
are exceptions. We came across it, while trying to understand Ruibang's latest
paper "[SOAP3-dp: Fast, Accurate and Sensitive GPU-Based Short Read Aligner](h
ttp://www.plosone.org/article/info%3Adoi%2F10.1371%2Fjournal.pone.0065632)"
published in PLOS One today. It will be covered in a future commentary.

For source code and other details, please check [DNA Indexing and Alignment
Tools](http://i.cs.hku.hk/2bwt-tools/index.php) at Hong Kong University.

