---
title: High-throughput Pairing of T Cell Receptor Alpha and Beta Sequences
tags: []
categories:
- blog
---
Readers may find [this paper](http://stm.sciencemag.org/content/7/301/301ra131
.figures-only) by Bryan Howie and colleagues interesting. It solves an
important problem (finding pairing pattern of TCR alpha and beta chains) using
high-throughput sequencing and an elegant mathematical model.
<!--more-->

> The T cell receptor (TCR) protein is a heterodimer composed of an alpha
chain and a beta chain. TCR genes undergo somatic DNA rearrangements to
generate the diversity of T cell binding specificities needed for effective
immunity. Recently, high-throughput immunosequencing methods have been
developed to profile the TCR alpha (TCRA) and TCR beta (TCRB) repertoires.
However, these methods cannot determine which TCRA and TCRB chains combine to
form a specific TCR, which is essential for many functional and therapeutic
applications. We describe and validate a method called pairSEQ, which can
leverage the diversity of TCR sequences to accurately pair hundreds of
thousands of TCRA and TCRB sequences in a single experiment. Our TCR pairing
method uses standard laboratory consumables and equipment without the need for
single-cell technologies. We show that pairSEQ can be applied to T cells from
both blood and solid tissues, such as tumors.

Their probabilistic model is very familiar to me, because twelve years back I
used it in a different context - [for finding clustered proteins from noisy
large-scale protein-protein interaction
data](http://www.pnas.org/content/100/22/12579.full). Here is the basic idea.
If A has 10 friends and B has 10 friends, what is the probability that they
have 9 common friends (by chance alone)? If the computed probability is very
low and the actual measurement shows that they indeed have 9 common friends,
that means A and B are strongly associated. In case of TCR alpha and beta
chains in their experimental set-up, that strong association implies their
combining to form heterodimers. For large-scale protein-protein interaction
data in yeast, significant association appeared to show functional similarity.

The work for the above TCR paper was done by Adaptive Technologies, a very
creative Seattle-based company that was founded by scientists from Fred Hutch
Cancer Research Institute.

