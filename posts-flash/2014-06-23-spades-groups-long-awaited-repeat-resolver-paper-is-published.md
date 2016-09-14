---
title: 'SPAdes Group''s  Long-awaited Repeat Resolver Paper is Published '
tags: []
categories:
- blog
---
Readers may take a look at the new paper published by Pavel Pevzner's group.
We had been eagerly waiting for the results since Anton Korobeynikov mentioned
them in a blog comment months back.
<!--more-->

[ExSPAnder: a universal repeat resolver for DNA fragment
assembly](http://bioinformatics.oxfordjournals.org/content/30/12/i293.full)

> Next-generation sequencing (NGS) technologies have raised a challenging de
novo genome assembly problem that is further amplified in recently emerged
single-cell sequencing projects. While various NGS

assemblers can use information from several libraries of read-pairs, most of
them were originally developed for a single library and do not fully benefit
from multiple libraries. Moreover, most assemblers assume uniform read
coverage, condition that does not hold for single-cell projects where
utilization of read-pairs is even more challenging. We have developed an
exSPAnder algorithm that accurately resolves repeats in the case of both
single and multiple libraries of read-pairs in both standard and single-cell
assembly projects.

For context, it is fairly easy to construct contigs from de Bruijn graphs of
short reads, but filling the region between contigs is a major challenge.
Velvet paper used a method incorporating ideas from Gene Myers' 2000
Drosophila paper and other assembly programs also developed their own ideas
(e.g. repeat resolution module in SOAPdenovo), but (based on my understanding)
Pevzner had been trying to get a formal and generalized solution useful in
many cases. They published a number of papers over last four years and we
previously covered some of them in this blog (check links related to
[Rectangular Graph](http://www.homolog.us/blogs/blog/category/genome-
assembly-2/rectangular-graph-genome-assembly-2/)).

The novelty of ExSPAnder over previous approaches from the same group is in
their use of scoring function. How is that different from Ray? From the paper
(emphasis ours) -

> In addition to function ScoreP(e), EXSPANDER uses a decision rule Extend(P)
that either chooses one of the extension edges to extend the path P or makes
the decision to stop growing this path beyond the ending vertex of P. The
procedure is iterated over all the paths until no path can be further
extended. To initiate this algorithm one can start with a set of single-edge
paths formed by all sufficiently long edges in the assembly graph. The
resulting paths are output as contigs after removing the paths that are
contained within other paths as well as removing non-informative overlaps
(i.e. suffixes of paths that represent prefixes of other paths).

This simple approach is merely a framework and, depending on the specifics of
the scoring function and the decision rule, it

can be either efficient (like in the Ray assembler) or disastrous.

The authors of Telescoper made an attempt to improve on Rays

scoring function and to substantiate it with rigorous statistical

analysis. **However, scoring functions in both Ray and Telescoper

are not universal, e.g. they assume the uniform genome coverage

by reads, condition that does not hold for single-cell data.**

We will continue to dig into their algorithm more and keep you posted.

