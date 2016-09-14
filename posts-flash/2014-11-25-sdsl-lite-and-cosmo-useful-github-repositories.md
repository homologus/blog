---
title: Sdsl-lite and Cosmo - Useful Github Repositories
tags: []
categories:
- blog
---
Readers interested in doing genome assembly with low memory will find the
following two github repositories useful. They are related to Christina
Boucher et al's recent ['variable-Order de Bruijn graphs'
paper](http://www.homolog.us/blogs/blog/2014/11/14/variable-order-de-bruijn-
graphs/), but research along the same line started a long time back. For
example, check our [Succinct de Bruijn Graphs from Tetsuo Shibuyas Group
](http://www.homolog.us/blogs/blog/2012/10/08/succinct-de-bruijn-graphs-from-
tetsuo-shibuyas-group/)posted in 2012 and Alex Bowe's [Succinct de Bruijn
Graphs](http://alexbowe.com/succinct-debruijn-graphs/).
<!--more-->

1\. Succinct Data Structure Library 2.0 (simongog/sdsl-lite) can be accessed
[here](https://github.com/simongog/sdsl-lite).

>

SDSL - Succinct Data Structure Library

What is it?

The Succinct Data Structure Library (SDSL) is a powerful and flexible C++11
library implementing succinct data structures. In total, the library contains
the highlights of 40 research publications. Succinct data structures can
represent an object (such as a bitvector or a tree) in space close the
information-theoretic lower bound of the object while supporting operations of
the original object efficiently. The theoretical time complexity of an
operations performed on the classical data structure and the equivalent
succinct data structure are (most of the time) identical.

2\. Cosmo (alexbowe/cosmo) is a fast, low-memory DNA assembler using a
succinct (variable order) de Bruijn graph and can be accessed
[here](https://github.com/alexbowe/cosmo).

