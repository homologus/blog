---
title: Bounds from a Card Trick
tags: []
categories:
- blog
---
It is well-known that Claude Shannon, the father of information theory, spent
all his days [at Bell labs playing chess and thinking about Chess
moves](http://www.pi.infn.it/~carosi/chess/shannon.txt). In the same vein,
maybe the best ideas of modern day bioinformatics will come from those, who
'waste their time' playing card :)
<!--more-->

[Link](http://arxiv.org/pdf/1011.4609v1.pdf)

> We describe a new variation of a mathematical card trick, whose analysis
leads to new lower bounds for data compression and estimating the entropy of
Markov sources.

Several years ago, an article in the popular press [1] described the following
mathematical card trick: the magician gives a deck of cards to an audience
member, who cuts the deck, draws six cards and lists their colours; the
magician then says which cards were drawn. The key to the trick is that the
magician prearranges the deck so that the sequence of the cards colours is a
substring of a binary De Bruijn cycle of order six, i.e., so that every
sextuple of colours occurs at most once. Although the trick calls only for the
magician to name the cards drawn, he or she could also name the next card, for
example, with absolute certainty. At the time we ran across the article, we
were studying empirical entropy, and one way to de?ne the kth-order empirical
entropy of a string s is as our expected uncertainty about the character in a
randomly chosen position when given the preceding k characters [2]. After
reading the tricks description, it occurred to us that the kth-order empirical
entropy of any De Bruijn cycle of order at most k is 0. Using this and other
properties of De Bruijn cycles, we were able to prove several lower bounds for
data compression [3, 4].

If you do not understand the context of this commentary, it is related to a
very cool paper from Rayan Chikhi and collaborators that we are not supposed
to talk about :). They supposedly compress de Bruijn graphs into 3.5-4.5
bits/kmer, which is close to the theoretical limit of 2.43 bits per k-mer
derived in their paper !!

