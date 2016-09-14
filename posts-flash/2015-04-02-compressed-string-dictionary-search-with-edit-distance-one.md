---
title: Compressed String Dictionary Search with Edit Distance One
tags: []
categories:
- blog
---
[Today's must read theoretical
paper](http://link.springer.com/article/10.1007/s00453-015-9990-0#page-1) \-
(h/t: @tony cox)
<!--more-->

> In this paper we present different solutions for the problem of indexing a
dictionary of strings in compressed space. Given a pattern P, the index has to
report all the strings in the dictionary having edit distance at most one with
P. Our first solution is able to solve queries in (almost optimal) O(|P|+occ)
time where occ is the number of strings in the dictionary having edit distance
at most one with P. The space complexity of this solution is bounded in terms
of the kth order entropy of the indexed dictionary. A second solution further
improves this space complexity at the cost of increasing the query time.
Finally, we propose randomized solutions (Monte Carlo and Las Vegas) which
achieve simultaneously the time complexity of the first solution and the space
complexity of the second one.

The work is an extended version of the paper [8] appeared in Proceedings of
23rd Annual Symposium on Combinatorial Pattern Matching, 2012.

