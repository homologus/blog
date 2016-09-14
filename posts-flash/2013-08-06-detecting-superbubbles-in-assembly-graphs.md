---
title: Detecting Superbubbles in Assembly Graphs
tags: []
categories:
- blog
---
Kunihiko Sadakane and Tetsuo Shibuya do very creative work on algorithm
development, and we covered their papers in several earlier commentaries.
<!--more-->

[Succinct de Bruijn Graphs from Tetsuo Shibuyas
Group](http://www.homolog.us/blogs/blog/2012/10/08/succinct-de-bruijn-graphs-
from-tetsuo-shibuyas-group/).

[More on Succint de Bruijn Graph](http://www.homolog.us/blogs/blog/2013/07/03
/more-on-succint-de-bruijn-graph/)

@sjackman forwarded the following paper from the same group that the readers
will find interesting.

[Link](http://arxiv.org/abs/1307.7925)

> We introduce a new concept of a subgraph class called a superbubble for
analyzing assembly graphs, and propose an efficient algorithm for detecting
it. Most assembly algorithms utilize assembly graphs like the de Bruijn graph
or the overlap graph constructed from reads. From these graphs, many assembly
algorithms first detect simple local graph structures (motifs), such as tips
and bubbles, mainly to find sequencing errors. These motifs are easy to
detect, but they are sometimes too simple to deal with more complex errors.
The superbubble is an extension of the bubble, which is also important for
analyzing assembly graphs. Though superbubbles are much more complex than
ordinary bubbles, we show that they can be efficiently enumerated. We propose
an average-case linear time algorithm (i.e., O(n+m) for a graph with n
vertices and m edges) for graphs with a reasonable model, though the worst-
case time complexity of our algorithm is quadratic (i.e., O(n(n+m))).
Moreover, the algorithm is practically very fast: Our experiments show that
our algorithm runs in reasonable time with a single CPU core even against a
very large graph of a whole human genome.

On the same topic, here is another interesting paper forwarded by @sjackman:

[A polynomial delay algorithm for the enumeration of bubbles with length
constraints in directed graphs and its application to the detection of
alternative splicing in RNA-seq data](http://arxiv.org/abs/1307.7813)

> We present a new algorithm for enumerating bubbles with length constraints
in directed graphs. This problem arises in transcriptomics, where the question
is to identify all alternative splicing events present in a sample of mRNAs
sequenced by RNA-seq. This is the first polynomial-delay algorithm for this
problem and we show that in practice, it is faster than previous approaches.
This enables us to deal with larger instances and therefore to discover novel
alternative splicing events, especially long ones, that were previously
overseen using existing methods.

They are all related to WABI 2013.

