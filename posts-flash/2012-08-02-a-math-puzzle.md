---
title: A Math Puzzle
tags: []
categories:
- blog
---
Our reader Andrew Brommage left us with a math puzzle in [the comment
section](http://www.homolog.us/blogs/2012/07/30/when-is-your-birthday/) \-
<!--more-->

> Mathematically-minded readers may wish to try proving this as an exercise.
The task is to analyse what happens to N (1 e^(-1/?N) (1 + 1/?N)) as N??

Any taker? The question is related to optimal design of hash functions.

\--------------------

Speaking of mathematical formula, we would like to include a separate but
related derivation in this commentary. It estimates the probability of false
positive of a Bloom filter.

Bloom filter is a probabilistic data structure to [help us count the number of
k-mers](http://www.homolog.us/blogs/2012/03/28/efficient-methods-for-
counting-k-mers/) in an NGS library using less amount of RAM than hashes. It
utilizes the fact that larger number of k-mers in a deep-sequenced NGS library
[come from sequencing errors than the underlying
genome](http://www.homolog.us/blogs/2011/09/20/maximizing-utility-of-
available-rams-in-k-mer-world/).

[Bloom filter](http://en.wikipedia.org/wiki/Bloom_filter) uses multiple hash
functions (k) to insert each element into a bit array. It is probabilistic,
because if a k-mer is found in the bit array, that k-mer may or may not be
present in the data set. However, if a k-mer is not found in the bit array, it
is definitely absent from the data set. You can [play with a Bloom filter
here](http://llimllib.github.com/bloomfilter-tutorial/) to see how it works.

Bloom filter is designed based on multiple parameters, and a mathematical
understanding of their relationship with false positive rate is needed for
proper choice of parameters. You can find an well-explained derivation of
probability of false positives [here](http://en.wikipedia.org/wiki/Bloom_filte
r#Probability_of_false_positives).

