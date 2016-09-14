---
title: External Memory Generalized Suffix and LCP Arrays Construction
tags: []
categories:
- blog
---
Felipe A. Louza, one of our readers, posted [link to his
paper](http://www2.icmc.usp.br/~louza/index.php?page=publications) that others
may find helpful. It is accepted at 24th Annual Symposium on Combinatorial
Pattern Matching (CPM 2013).
<!--more-->

> A suffix array is a data structure that, together with the LCP array, allows
solving many string processing problems in a very efficient fashion. In this
article we introduce eGSA, the first external memory algorithm to construct
both generalized suffix and LCP arrays for sets of strings. Our algorithm
relies on a combination of buffers, induced sorting and a heap. Performance
tests with real DNA sequence sets of size up to 8.5 GB showed that eGSA can
indeed be applied to sets of large sequences with efficient running time on a
low-cost machine. Compared to the algorithm that most closely resembles eGSA
purpose, eSAIS, eGSA reduced the time spent to construct the arrays by a
factor of 2.54.8.

Our previous threads on similar topic are -

[On Constructing Suffix Arrays and LCP Arrays in External
Memory](http://www.homolog.us/blogs/2013/01/28/on-constructing-suffix-arrays-
and-lcp-arrays-in-external-memory/)

[Construction of Suffix Array in External Memory Follow
Up](http://www.homolog.us/blogs/2013/02/21/construction-of-suffix-array-in-
external-memory-follow-up/)

Also, in this context, we like to mention another (old) paper that readers may
enjoy. We believe we first saw it by digging through Jared Simpson's SGA code.

[Dynamic Extended Suffix Arrays](http://www-igm.univ-
mlv.fr/~lecroq/articles/jda2009.pdf)

by M. Salson, T. Lecroq, M. Leonard, L. Mouchard.

> In this article, we are presenting an algorithm that modifi es the suffix
array and the Longest Common Prefix (LCP) array when the text is edited
(insertion, substitution or deletion of a letter or a factor). This algorithm
is based on a recent four-stage algorithm developed for dynamic Burrows-
Wheeler Transforms (BWT). For minimizing the space complexity, we are sampling
the Suffix Array, a technique used in BWT-based compressed indexes. We
furthermore explain how this technique can be adapted for maintaining a sample
of the Extended Suffix Array, containing a sample of the Suffix Array, a
sample of the Inverse Suffix Array and the whole LCP array. Our practical
experiments show that it operates very well in practice, being quicker than
the fastest suffix array construction algorithm.

Slides:

[Dynamic Burrows Wheeler Transform](http://www-igm.univ-
mlv.fr/~lecroq/talks/ISW4_Laurent.pdf)

