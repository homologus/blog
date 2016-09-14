---
title: Understanding the Algorithm behind Pbdagcon and POA for Multiple Sequence Alignment
tags: []
categories:
- blog
---
If you are trying to understand how pbdagcon from Pacbio (Jason Chin) and POA
(Partial Order Alignment) within Jared Simpson's nanopolish work,you may find
[Jonathan Dursi's post in Simpson's
blog](https://simpsonlab.github.io/2015/05/01/understanding-poa/) helpful. We
will update the next version of Pandora's Toolbox manual (freely available
[here](https://leanpub.com/pandoras-toolbox)) to include a discussion on these
algorithms.
<!--more-->

> This post gives a quick lower-level overview of the steps in the POA
algorithm, with a simple implementation in python to demonstrate the ideas
more concretely.

**The Basics**

The insight of the first POA paper was that flattening of the alignment of
sequences leads to meaningless artifacts that, while largely harmless for
pairwise alignments or even multiple alignments of strongly conserved
sequences, causes problems with more general multiple alignments. For
instance, consider the following sequences:

>seq1

CCGCTTTTCCGC

>seq2

CCGCAAAACCGC

There is ambiguity in selecting a single, best alignment between this pair of
sequences; for instance below are 4 of 28 = 256 nearly equivalent ways of
expressing this pairwise alignment. The best alignment will depend on the
particular gap-scoring scheme used.

Continue reading [here](https://simpsonlab.github.io/2015/05/01/understanding-
poa/).

