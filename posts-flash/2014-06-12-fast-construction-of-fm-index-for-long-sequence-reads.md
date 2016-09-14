---
title: Fast construction of FM-index for long sequence reads
tags: []
categories:
- blog
---
We [mentioned Heng Li's ropebwt2 code at
github](http://www.homolog.us/blogs/blog/2013/10/27/heng-li-releases-
ropebwt2/) in the past, but now he discloses the algorithm in [a brief paper
posted at arxiv](http://arxiv.org/abs/1406.0426). We will spend the rest of
the day trying to understand what is going on.
<!--more-->

> Summary: We present a new method to incrementally construct the FM-index for
both short and long sequence reads, up to the size of a genome. It is the
first algorithm that can build the index while implicitly sorting the
sequences in the reverse (complement) lexicographical order without a separate
sorting step. The implementation is among the fastest for indexing short reads
and the only one that practically works for reads of averaged kilobases in
length. Availability and implementation: https://github.com/lh3/ropebwt2
Contact: hengli@broadinstitute.org

Is constructing FM index still relevant in the 'Minimizer' world?

\-------------------

Edit.

Rayan Chikhi worked through an example
[here](https://gist.github.com/rchikhi/20fa292238082130669a) that you will
find helpful.

>

Algorithm 1 - Illustration

\--------------------------

Algorithm 1 is InsertIO1(B,P) in the paper, which takes as input:

B (the BWT of a string T#, where # is a sentinel character)

P (any string)

It outputs BWT(T#P$), where $ is a character lexicographically larger than #,

but lexicographically smaller than all other letters.

An order of sentinels is introduced in the Methods section of the paper

($_0 < $_1 < ... < $_(m-1)), but not in the presentation of Algorithm 1.

Yet, it is important.

We will later see that Algorithm 1 would be incorrect if we considered that #
= $.

Let's run Algorithm 1 on an example: InsertIO1(B = "ar#ab", P = "da")

Recall the segmentation of B, taking into account the new characters in da$,
is:

B_# B_$ B_a B_b B_d B_r,

where

B_# = "a"

B_$ = ""

B_a = "r#"

B_b = "a"

B_d = ""

B_r = "b".

The steps of the Algorithm are:

