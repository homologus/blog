---
title: Going Through the Lyndom Word Paper
tags: []
categories:
- blog
---
Few days back we mentioned a paper by Mantaci, Restivo, Rosone and Sciortino
in the commentary titled "[Lyndon Word and Lyndon
Factorization](http://www.homolog.us/blogs/blog/2013/08/07/lyndon-word-and-
lyndon-factorization/)". We finally got time to understand the math, or at
least make a modest attempt to understand.
<!--more-->

The paper presents an elegant way to construct the BWT and Suffix array of a
text.

> The goal of this paper is to propose a new strategy to compute the bwt and
the SA of a text by decomposing it into Lyndon factors and by using the
compatibility relation between the sorting of its local and global suffixes.

**Lyndon Word**

You start with a word and take all its rotated forms. The lexicographically
smallest one is the Lyndon word.

LYNDON

YNDONL

NDONLY

DONLYN

ONLYND

NLYNDO

Which one the smallest among above six? It is DONLYN.

> Alternately, a Lyndon word has the property that, whenever it is split into
two substrings, the left substring is always lexicographically less than the
right substring.

DONLYN also passes the above test. It is a Lyndon word.

Please note that words like ATATATAT are not Lyndon words. Periodic words are
not allowed and Lexicographically smallest one has to be uniquely defined.

The concept of Lyndon word was proposed by mathematician Roger Lyndon in 1954.

**Lyndon Factorization**

Lyndon showed in 1958 that any long text could be broken into a series of
Lyndon words.

> Every word W ? + has a unique factorization W = L_1 L_2 L_k such that L_1
?lex ?lex L_k is a non-increasing sequence of Lyndon words.

However, it took until 1983, when Duval presented a linear time algorithm to
perform the above factorization for any given word.

One key aspect of Duval's method is that the program can start from the left
of a word and get the Lyndon factorizations one by one until reaching the
right end. Why that is important will be clear in the next section.

**BWT and Suffix Array Through Lyndon Factorization**

Mantaci, Restivo, Rosone and Sciortino paper presents a highly parallelizable
way of computing BWT and SA by using Lyndon factorization.

>

This proposition suggests a possible strategy for sorting the list of the
suffixes of

some word W:

find the Lyndon decomposition of W, L_1L_2 L_k;

find the sorted list of the suffixes of L_1 and, separately, the sorted list
of the

suffixes of L_2;

merge the sorted lists in order to obtain the sorted lists of the suffixes of
L_1L_2;

find the sorted list of the suffixes of L_3 and merge it to the previous
sorted list;

keep on this way until all the Lyndon factors are processed;

You can now guess why Duval's method is helpful. You can have multiple
parallel threads running for BWT computation, with one set finding the Lyndon
factorization and other set computing the BWT on the already factorized part
of the text. The BWT computation method through merging of parts is explained
in the following example.

> Let W = aabcabbaabaabdabbaaabbdc. The Lyndon factorization of W is
L_1L_2L_3, where L_1 = aabcabb > L_2 = aabaabdabb > L_3 = aaabbdc.

![Capture](http://www.homolog.us/blogs/wp-
content/uploads/2013/08/Capture43-300x243.png)

What is going on? BWT and SA computation of the first Lyndon word
(L_1=aabcabb) is trivial. For the second one, 7 is being added to each Suffix
array location, 7 being the size of L_1. Additionally, the G array describes
how to insert the SA of L_2 within the SA of L_1 to get the SA of L_1 L_2. The
process is continued until all Lyndon factorizations are incorporated.

We are continuing to read the paper. If we have any more insight, we will add
that below.

\----------------------------------

Relevant links -

http://en.wikipedia.org/wiki/Lexicographically_minimal_string_rotation

http://stackoverflow.com/questions/3459509/minimal-cyclic-shift-algorithm-
explanation

http://www.ics.uci.edu/~eppstein/PADS/Lyndon.py

