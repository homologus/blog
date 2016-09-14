---
title: Cuckoo Filter to Replace Bloom Filter?
tags: []
categories:
- blog
---
@rozovr forwarded the link to a new paper that is worth looking into.
<!--more-->

[Cuckoo Filter: Practically Better Than
Bloom](http://www.cs.cmu.edu/~dga/papers/cuckoo-conext2014.pdf)

> In many networking systems, Bloom filters are used for high speed set
membership tests. They permit a small fraction of false positive answers with
very good space efficiency. However, they do not permit deletion of items
from the set, and previous attempts to extend standard Bloom filters to
support deletion all degrade either space or performance. We propose a new
data structure called the cuckoo filter that can replace Bloom filters for
approximate set membership tests. Cuckoo filters support adding and removing
items dynamically while achieving even higher performance than Bloom filters.
For applications that store many items and target moderately low false
positive rates, cuckoo filters have lower space overhead than space-optimized
Bloom filters. Our experimental results also show that cuckoo filters
outperform previous data structures that extend Bloom filters to support
deletions substantially in both time and space.

The name derives from their use of Cuckoo hash scheme. Compared to Bloom
filter -

> We propose the cuckoo filter, a practical data structure that provides four
major advantages.

1\. It supports adding and removing items dynamically;

2\. It provides higher lookup performance than traditional Bloom filters, even
when close to full (e.g., 95% space utilized);

3\. It is easier to implement than alternatives such as the quotient filter;
and

4\. It uses less space than Bloom filters in many practical applications, if
the target false positive rate  is less than 3%.

For more information, check their [google plus
thread](https://plus.google.com/u/0/116929526783308854537/posts/Fmm3dK27Ra9)
and [reddit thread](http://www.reddit.com/r/programming/comments/2juwef/cuckoo
_filters_better_than_bloom_filters/).

Will it replace Bloom filter based k-mer counting methods? Pall Melsted offers
his perspective -

![Capture](http://www.homolog.us/blogs/wp-
content/uploads/2014/10/Capture1-300x203.png)

