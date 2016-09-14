---
title: Probabilistic Data Structures - an Excellent Introduction
tags:
- Bloom filter
- Diginorm
categories:
- blog
---
Probabilistic data structures are being used to significantly cut down the
memory requirements of de Bruijn graphs. We discussed their application to NGS
world in earlier articles - [here](http://www.homolog.us/blogs/2012/03/29
/using-bloom-filter-a-simple-introduction-for-bioinformaticians/) and
[here](http://www.homolog.us/blogs/2012/07/19/quip-minia-slimgene-and-titus-
browns-paper-on-scaling-metagenome/).
<!--more-->

We found a blog post (hat tip: [Rayan
Chikhi](http://www.irisa.fr/symbiose/rayan_chikhi)) that provides excellent
introduction to probabilistic data structures. The context of the blog post is
the internet world, but many issues mentioned there are equally applicable to
those working on NGS. If you do not immediately recognize the similarity, here
is a clue. The typical questions asked for the 'random integer count' example
in the above blog post are identical to k-mer counting problem in NGS.

[Probabilistic Data Structures for Web Analytics and Data
Mining](http://highlyscalable.wordpress.com/2012/05/01/probabilistic-
structures-web-analytics-data-mining/)

The original Whang, Vander-Zaden, Taylor article that the above-mentioned blog
summarizes can be found at [this
link](http://dblab.kaist.ac.kr/Publication/pdf/ACM90_TODS_v15n2.pdf).

