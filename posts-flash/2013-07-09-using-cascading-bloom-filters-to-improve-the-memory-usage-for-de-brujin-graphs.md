---
title: Using Cascading Bloom Filters to Improve the Memory Usage for de Brujin Graphs
tags: []
categories:
- blog
---
Today's must read paper [appeared in arxiv](http://arxiv.org/abs/1302.7278)
(emphasis ours).
<!--more-->

> De Brujin graphs are widely used in bioinformatics for processing next-
generation sequencing data. Due to a very large size of NGS datasets, it is
essential to represent de Bruijn graphs compactly, and several approaches to
this problem have been proposed recently. In this work, we show how to reduce
the memory required by the algorithm of [3] that represents de Brujin graphs
using Bloom filters. **Our method requires 30% to 40% less memory with respect
to the method of [3], with insignificant impact to construction time. At the
same time, our experiments showed a better query time compared to [3]. This
is, to our knowledge, the best practical representation for de Bruijn
graphs.**

Those unfamiliar with Minia can read our earlier commentaries.

[Top Bioinformatics Contributions of
2012](http://www.homolog.us/blogs/blog/2013/01/10/top-bioinformatics-
contributions-of-2012/).

[Quip, Minia, SlimGene and Titus Browns paper on Scaling
Metagenome](http://www.homolog.us/blogs/blog/2012/07/19/quip-minia-slimgene-
and-titus-browns-paper-on-scaling-metagenome/)

[Minia Assembler and French
Revolution](http://www.homolog.us/blogs/blog/2012/10/01/minia-assembly-
algorithm-and-french-revolution/)

P.S. Adding a twitter conversation in case the same question comes to your
mind, because five months later people will be chatting about different things
in twitter.

![Capture3](http://www.homolog.us/blogs/wp-
content/uploads/2013/07/Capture31-300x286.png)

