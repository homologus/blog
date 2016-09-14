---
title: Heng Li Releases Ropebwt2
tags: []
categories:
- blog
---
We discussed BCR algorithm and related topics on BWT construction from short
reads many times ([here - check comment
section](http://www.homolog.us/blogs/blog/2013/05/14/external-memory-
generalized-suffix-and-lcp-arrays-construction/),
[here](http://www.homolog.us/blogs/blog/2013/08/14/a-constant-space-
comparison-based-algorithm-for-computing-the-burrows-wheeler-transform/),
[here](http://www.homolog.us/blogs/blog/2013/07/20/bioinformatics-patents-on-
burrows-wheeler-transform/) and
[here](http://www.homolog.us/blogs/blog/2013/08/07/lyndon-word-and-lyndon-
factorization/)). Readers may find [the following
implementation](https://github.com/lh3/ropebwt2) useful (h/t: @rayanchikhi).
Version 1 of this code is an important component of SGA assembler.
<!--more-->

> RopeBWT2 is an experimental tool for constructing the FM-index for a
collection of DNA sequences. It works by incrementally inserting multiple
sequences into an existing pseudo-BWT position by position, starting from the
end of the sequences. This algorithm can be largely considered a mixture of
BCR and dynamic FM-index. Nonetheless, ropeBWT2 is unique in that it may
implicitly sort the input into reverse lexicographical order (RLO) or reverse-
complement lexicographical order (RCLO) while building the index.

The [github page](https://github.com/lh3/ropebwt2) has good description on how
to run the code and there is no point in copying everything here. Those
interested in learning what is being implemented will find the following
discussion helpful.

>

**Methods Overview**

RopeBWT2 keeps the entire BWT in six B+ trees with the i-th tree storing the
substring B[C(i)+1..C(i+1)], where C(i) equals the number of symbols
lexicographically smaller than i. In each B+ tree, an internal node keeps the
count of symbols in the subtree decending from it; an external node keeps a
BWT substring in the run-length encoding. The B+ tree achieve a similar
purpose to the rope data structure, which enables efficient query and
insertion. RopeBWT2 uses this rope-like data structure to achieve incremental
construction. This is where word 'rope' in ropeBWT2 comes from.

The original BCR implementation uses static encoding to keep BWT. Although it
is possible to insert strings to an existing BWT, we have to read through the
old BWT. Reading the entire BWT may be much slower than the actual insertion.
With the rope data structure, we can insert one or a few sequences of length m
in O(mlogn) time without reading all the BWT. We can thus achieve efficient
incremental construction.

To achieve RLO for one-string insertion, we insert the symbol that is ahead of
a suffix at the position based on the rank of the suffix computed from
backward search. Inserting multiple strings in RLO is essentially a
combination of radix sort, BCR and single-string insertion. RopeBWT2 uses
radix sort to group symbols with an identical suffix, compute the rank of the
suffix with backward search and insert the group of symbols based on the BCR
theory. For RCLO, we find the insertion points with the complemented sequence
but insert with the original string.

**RopeBWT2 vs. ropeBWT**

RopeBWT is the predecessor of ropeBWT2. The old version implements three
separate algorithms: in-memory BCR, single-string incremental FM-index on top
of a B+ tree and single-string incremental FM-index on top of a red-black
tree. BCR is later extended to support RLO and RCLO as well.

The BCR implementation in ropeBWT is the fastest so far for short reads,
faster than ropeBWT2. The legacy BCR implementation is still the preferred
choice for constructing the FM-index of short reads for the assembly purpose.
However, with parallelized incremental multi-string insertion, ropeBWT2 is
faster than ropeBWT for incremental index construction and works much better
with long strings. RopeBWT2 also uses more advanced run-length encoding, which
will be more space efficient for highly repetitive inputs and opens the
possibility for inserting a run in addition individual symbols.

**RopeBWT2 vs. BEETL**

BEETL is the original implementation of the BCR algorithm. It uses disk to
alleviate the memory requirement for constructing large FM-index and therefore
heavily relies on fast linear disk access. BEETL supports the SAP order for
inserting sequences but not RLO or RCLO.

**RopeBWT2 vs. dynamic FM-index**

RopeBWT was conceived in 2012, but the algorithm has been invented several
years earlier for multiple times. Dynamic FM-index is a notable implementation
that uses a wavelet tree for generic text and supports the deletion operation.
As it is not specifically designed for DNA sequences, it is apparently ten
times slower and uses more memory on the index construction.

