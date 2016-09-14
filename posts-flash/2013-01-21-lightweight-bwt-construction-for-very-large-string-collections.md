---
title: Lightweight BWT Construction for Very Large String Collections
tags: []
categories:
- blog
---
[Slides from a very good
presentation](http://lonati.di.unimi.it/prinvarese2011/talks/rosone.pdf)
<!--more-->

\--------------------------------------

You can find the related paper
[here](http://www.sciencedirect.com/science/article/pii/S0304397512001211).

>

**Lightweight algorithms for constructing and inverting the BWT of string collections**

_Markus J. Bauera, Anthony J. Coxa, Giovanna Rosone_

Recent progress in the field of DNA sequencing motivates us to consider the
problem of computing the BurrowsWheeler transform (BWT) of a collection of
strings. A human genome sequencing experiment might yield a billion or more
sequences, each 100 characters in length. Such a dataset can now be generated
in just a few days on a single sequencing machine. Many algorithms and data
structures for compression and indexing of text have the BWT at their heart,
and it would be of great interest to explore their applications to sequence
collections such as these. However, computing the BWT for 100 billion
characters or more of data remains a computational challenge.

In this work we address this obstacle by presenting a methodology for
computing the BWT of a string collection in a lightweight fashion. A first
implementation of our algorithm needs O(mlogm) bits of memory to process m
strings, while a second variant makes additional use of external memory to
achieve RAM usage that is constant with respect to m and negligible in size
for a small alphabet such as DNA. The algorithms work on any number of strings
and any size. We evaluate our algorithms on collections of up to 1 billion
strings and compare their performance to other approaches on smaller datasets.

We take further steps toward making the BWT a practical tool for processing
string collections on this scale. First, we give two algorithms for recovering
the strings in a collection from its BWT. Second, we show that if sequences
are added to or removed from the collection, then the BWT of the original
collection can be efficiently updated to obtain the BWT of the revised
collection.

\-----------------------

While on the topic of BWT construction, let us link two other relevant papers
for linear time suffix array construction -

[Linear Suffix Array Construction by Almost Pure

Induced-Sorting - Nong, Zhang, Chan

[google code for SA-IS algorithm
above](https://sites.google.com/site/yuta256/sais)

[Efficient Implementations of Suffix Array

Construction Algorithms - Lee, Park

I presume everyone can find out Ko-Aluru paper that precedes them, and we do
not need to put up a link. Instead of trying to navigate through original
paper, you may try [these
slides](http://www.cs.helsinki.fi/u/tpkarkka/opetus/11s/spa/lecture11.pdf) to
learn about induced sorting.

