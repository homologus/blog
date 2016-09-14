---
title: Optimal Assembly for High Throughput Shotgun Sequencing
tags: []
categories:
- blog
---
How to judge how good a genome assembly algorithm is ? Mathematically inclined
readers may take a look at an interesting paper [submitted to
arxiv.org](http://arxiv.org/pdf/1301.0068v1.pdf).
<!--more-->

>

DNA sequencing is the basic workhorse of modern day biology and medicine.
Shotgun sequencing is the dominant technique used: many randomly located short
fragments called reads are extracted from the DNA sequence, and these reads
are assembled to reconstruct the original sequence. During the last two
decades, many assembly algorithms have been proposed, but comparing and
evaluating them is difficult. To clarify this, we ask: Given N reads of length
L sampled from an arbitrary DNA sequence, is it possible to achieve some
target probability 1? of successful reconstruction? We show that the answer
depends on the repeat statistics of the DNA sequence to be assembled, and we
compute these statistics for a number of reference genomes. We construct lower
bounds showing that reconstruction is impossible for certain choices of N and
L, and complement this by analytically deriving the performance of several
algorithms, both in terms of repeat statistics. In seeking an algorithm that
matches the lower bounds on real DNA data, we are able to methodically
progress towards an optimal assembly algorithm. The goal of this work is to
advocate a new systematic approach to the design of assembly algorithms with
optimality or near-optimality guarantee.

