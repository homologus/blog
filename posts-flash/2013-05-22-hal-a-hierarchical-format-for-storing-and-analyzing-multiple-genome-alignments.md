---
title: 'HAL: a Hierarchical Format for Storing and Analyzing Multiple Genome Alignments'
tags: []
categories:
- blog
---
David Haussler's lab, where Daniel Zerbino (of Velvet fame) is currently
working, published an [interesting paper on storing data from multiple
genomes](http://bioinformatics.oxfordjournals.org/content/29/10/1341.long).
Glenn Hickey is the first author.
<!--more-->

> We present HAL, a compressed, graph-based hierarchical alignment format for
storing multiple genome alignments and ancestral reconstructions. HAL graphs
are indexed on all genomes they contain.

In more details -

> HALs design was guided by two observations: (i) breakpoint graphs are the
most natural way of representing genome rearrangements (Pevzner and Tesler,
2003) and (ii) progressive alignment (based on a phylogenetic decomposition)
has been the most successful heuristic for multiple sequence alignment
(Notredame, 2007) and is likely to remain so for whole-genome alignment. A HAL
graph, therefore, decomposes a multiple alignment into a set of pairwise
alignments, which are represented as breakpoint graphs. Each pairwise
alignment corresponds to a branch of a rooted phylogenetic tree. In the
absence of a tree, a reference genome can be used as a root with all other
genomes as leaves.

A genome in HAL is represented by up to three arrays (Fig. 1A): a sequence
array, a top segment array if the genome has an ancestor in the tree and a
bottom segment array if the genome has one or more descendants in the tree.

**Availability**: All documentation and source code for the HAL API and tools are freely available at http://github.com/glennhickey/hal. 

We will add more, when we get a chance to go through the technical details.

