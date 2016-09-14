---
title: Safe and Complete Contig Assembly via Omnitigs
tags: []
categories:
- blog
---
<!--more-->

> Contig assembly is the first stage that most assemblers solve when
reconstructing a genome from a set of reads. Its output consists of contigs --
a set of strings that are promised to appear in any genome that could have
generated the reads. From the introduction of contigs 20 years ago, assemblers
have tried to obtain longer and longer contigs, but the following question was
never solved: given a genome graph G (e.g. a de Bruijn, or a string graph),
what are all the strings that can be safely reported from G as contigs? In
this paper we finally answer this question, and also give a polynomial time
algorithm to find them. Our experiments show that these strings, which we call
omnitigs, are 66% to 82% longer on average than the popular unitigs, and 29%
of dbSNP locations have more neighbors in omnitigs than in unitigs.

[Link](http://arxiv.org/abs/1601.02932)
