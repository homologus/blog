---
title: Compressed Spaced Suffix Arrays
tags: []
categories:
- blog
---
In today's [good paper column](http://arxiv.org/pdf/1312.3422v1.pdf) (h/t:
@tonycox)
<!--more-->

> Spaced seeds are important tools for similarity search in bioinformatics,
and using several seeds together often signi?cantly improves their
performance. With existing approaches, however, for each seed we keep a
separate linear-size data structure, either a hash table or a spaced su?x
array (SSA). In this paper we show how to compress SSAs relative to normal
su?x arrays (SAs) and still support fast random access to them. We ?rst prove
a theoretical upper bound on the space needed to store an SSA when we already
have the SA. We then present experiments indicating that our approach works
even better in practice.

1\. Related papers -

M. Crochemore and G. Tischler. The gapped su?x array: A new index structure
for fast approximate matching. In Proceedings of the 17th Symposium on String
Processing and Information Retrieval (SPIRE), pages 359364, 2010.

P. Peterlongo, N. Pisanti, F. Boyer, and M.-F. Sagot. Lossless ?lter for
?nding long multiple approximate repetitions using a new data structure, the
bi-factor array. In Proceedings of the 12th Symposium on String Processing and
Information Retrieval (SPIRE), pages 179190, 2005.

2\. Key Problem and Contribution -

> Multiple seeds are now a popular and powerful tool for similarity search,
but they have a lingering ?aw: we keep a hash table or SSA for each seed, and
each instance of these data structures takes linear space. For example,
SHRiMP2s [6] index for the human genome takes 16 GB for each seed. In
contrast, Bowtie 2s [13] compressed SA for that genome takes only 2.5 GB. This
is because a normal SA (which supports only substring matching) can be
compressed such that the number of bits per character is only slightly greater
than the empirical entropy of the text. Unfortunately, the techniques for
compressing normal SAs do not seem to apply directly to SSAs.

In this paper we show how to compress SSAs relative to normal SAs and still
support fast random access to them. Whereas the normal SA for a text lists the
starting points of the su?xes of that text by those su?xes lexicographic
order, the SSA for a text and a spaced seed lists the starting points of the
subsequences with the right shape by those subsequences lexicographic

order. Intuitively, if the seed starts with many 1s, the SSA will be similar
to the SA.

More later, when we get time.

