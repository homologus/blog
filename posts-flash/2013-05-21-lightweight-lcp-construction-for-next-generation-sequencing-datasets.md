---
title: Lightweight LCP Construction for Next-Generation Sequencing Datasets
tags: []
categories:
- blog
---
Thanks to reader Heng Li, we came to know about a number of very good papers
on sequence comparison from Anthony J. Cox and his colleagues.
<!--more-->

[Lightweight LCP Construction for Next-Generation Sequencing
Datasets](http://arxiv.org/pdf/1305.0160.pdf)

[Adaptive reference-free compression of sequence quality
scores](http://arxiv.org/pdf/1305.0159.pdf)

[Comparing DNA sequence collections by direct comparison of compressed text
indexes](http://arxiv.org/pdf/1304.5535.pdf)

> Popular sequence alignment tools such as BWA convert a reference genome to
an indexing data structure based on the BurrowsWheeler Transform (BWT), from
which matches to individual query sequences can be rapidly determined. However
the utility of also indexing the query sequences themselves remains relatively
unexplored. Here we show that an all-against-all comparison of two sequence
collections can be computed from the BWT of each collection with the BWTs held
entirely in external memory, i.e. on disk and not in RAM. As an application of
this technique, we show that BWTs of transcriptomic and genomic reads can be
compared to obtain reference-free predictions of splice junctions that have
high overlap with results from more standard reference-based methods. Code to
construct and compare the BWT of large genomic data sets is available at
http://beetl.github.com/BEETL/ as part of the BEETL library.

[Large-scale compression of genomic sequence databases with the Burrows-
Wheeler transform](http://arxiv.org/pdf/1205.0192.pdf)

\-----------------------

You know what is crazy? The first paper is freely available from arxiv, but
Springer charges $30 minus 5 cents to let you see it from their website ! $30
for merely posting intellectual work by others on a website, when you do not
have to pay the intellectual contributors anything???

![Capture](http://www.homolog.us/blogs/wp-
content/uploads/2013/05/Capture26-300x154.png)

Oh, that is not all. There will be VAT on top of that, because government
thinks you derive the same pleasure by 'consuming' a BWT paper as others do by
flipping through Playboy magazine.

What a broken system !

