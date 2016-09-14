---
title: An Efficient Preprocessing Module for Joining Paired end Reads before Assembly
tags:
- Scaffolding
- Paired end
categories:
- blog
---
We came across [this interesting NGS assembly-related
poster](http://research.microsoft.com/en-
us/events/2012summerschool/davidsilver.pdf), while searching for 'google
sparseheap' online. It is being presented without comment. More analysis will
come twelve months later, when they submit their paper, get it peer-reviewed,
revised, peer-reviewed again, edited, proof-read and published :)
<!--more-->

>

**A one-step method for de novo genome assembly using short paired-end sequence reads 

**

David H. Silver and Itai Yanai

Department of Biology, Technion Israel Institute of Technology, Haifa, Israel

Genome sequencing is currently only possible by assembling short sequence
fragments of DNA by identifying overlapping regions. To help in this
computationally intensive task, large DNA regions can be sequenced from both
ends, yielding paired-end reads. Currently however, paired-end information is
incorporated as an additional step following the assembly of contiguous
sequences (contigs). The underlying reason for this has been the notion that
this extra information derived from paired-end reads contributes mostly to
distinguishing repeat regions, rather than to the main task of assembling.
Here, we demonstrate that in fact the paired-end information is of tremendous
aid to the assembly process itself. Further, we present a mathematical model
which provides an explanatory framework for the success of our algorithm, thus
closing the big gap between the theory of de novo assembly and the practice.
Our algorithm benefits de novo genome assembling by a better assembly in terms
of sequence length with fewer assembly errors and requiring significantly less
sequence coverage.

