---
title: BWT Construction and K-mer Counting
tags: []
categories:
- blog
---
Over the last few weeks, we have been going through the algorithms of various
BWT construction and k-mer counting methods, and came to realize that they are
two sides of the same coin. That means the two communities can mutually
benefit from the improved algorithm/tools developed by each other. Our insight
is not novel, because Tallymer, a k-mer counting program from earlier
generation used suffix arrays and LCP arrays to perform k-mer counting in a
genome.
<!--more-->

Let us quickly explain the equivalence. Suppose you like to construct the BTW
of a small word - **JAMES$** . That is very easy to do, because you have go
through the increasing order of letters and then pick the letter right in
front of them. For example, $ is the smallest letter. So, our BWT will start
with S, which precedes $ immediately. A is the next small letter. So, S in BWT
will be followed by J, which precedes A. Following in that order, you get to
**SJM$AE** .

How about a more complicated word - **ONION$** ? In this case, we have two Os
and cannot proceed in the same way by ordering letters. However, we can take
the 3-mers and follow the same formula, because all 3-mers are unique.
Smallest two-mer is $ON. Therefore, the BWT starts with N, which precedes $.
The next 2-mer is ION. So, N will be followed by N, which precedes N.
Continuing in that manner, we can compute the BWT as **NNOOI$**.

The same method can be used for any large string as long we can define a k-mer
size so that all k-words become independent. But is it necessary for all
k-mers to be independent? What if that k-mer size is 10,000, because a genome
has a 10Kb block that is duplicate? Actually, one can find the BWT from a much
smaller k-mer size and infer the positions of letters preceding all unique
k-mers based on k-mer count. Then a small set of duplicate k-mers need to be
resolved by going to higher k-values.

Jared Simpson's SGA algorithm uses BWT/FM construction and string graph
traversal as two major steps. Given the equivalence of BWT construction with
k-mer counting and string graph with de Bruijn graph, SGA algorithm is
essentially similar to any dBG algorithm despite its apparent dissimilarity.

