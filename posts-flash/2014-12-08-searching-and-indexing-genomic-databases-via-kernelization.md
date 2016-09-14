---
title: Searching and Indexing Genomic Databases via Kernelization
tags: []
categories:
- blog
---
Rayan Chikhi reported about a new algorithm for searching through multiple
genomes using LZ77 (Lempel/Ziv) compression. It was presented by S. Puglisi at
the [Data Structures in
Bioinformatics](http://www.homolog.us/blogs/blog/2014/12/08/data-structures-
in-bioinformatics-workshop/) workshop.
<!--more-->

Those not attending the conference can check [this
paper](http://arxiv.org/abs/1412.1591) to know what it is about. (h/t:
@pmelsted). Readers may recall that Simon Puglisi is an author of another
outstanding paper that we reported about a month back (Alex Bowe's -
[Variable-Order de Bruijn Graphs](http://www.homolog.us/blogs/blog/2014/11/14
/variable-order-de-bruijn-graphs/)).

**Abstract:**

> The rapid advance of DNA sequencing technologies has yielded databases of
thousands of genomes. To search and index these databases e ffectively, it is
important that we take advantage of the similarity between those genomes.
Several authors have recently suggested searching or indexing only one
reference genome and the parts of the other genomes where they diff er. In
this paper we survey the twenty-year history of this idea and discuss its
relation to kernelization in parameterized complexity.

