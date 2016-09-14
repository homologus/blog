---
title: GraphMap for Fast and Sensitive Mapping of Long Noisy Reads
tags: []
categories:
- blog
---
Readers may find [this new
paper](http://biorxiv.org/content/biorxiv/early/2015/06/10/020719.full.pdf)
posted at arxiv interesting (h/t: Lex Nederbragt). Although the discussions in
the paper are tuned to Oxford Nanopore reads, I think the users of other long,
noisy read technologies (e.g. Pacbio) will see value in their aligner.
Therefore, I am surprised that the authors did not make any comparison with
[Gene Myers' DALIGNER](http://www.homolog.us/blogs/blog/2014/07/28/in-dalign-
paper-gene-myers-delivers-a-major-blow-to-his-biggest-competitor/).
<!--more-->

Given the performance gain over BLASR and BWA-MEM claimed in the paper, the
algorithm is worth taking a look. The aligner runs through five stages.

**1\. Region selection**

> GraphMap starts by roughly determining regions on the reference genome where
a read could potentially be aligned..... As a first step, region selection
relies on finding seeds between the query sequence and the reference, before
clustering them into candidate regions. For seed finding, .... we employed a
form of gapped spaced seeds similar to gapped q-gram filters for Levenshtein
distance....Specifically, we extended the approach proposed in Burkhardt and
Krkkinen11 to use both one- and two-gapped q-grams (Figure 1b) as detailed
below. This allows us to accommodate an arbitrary number of gaps in the
q-gram.

**2\. Graph-based vertex-centric construction of anchors**

> In this stage, we attempt to refine candidate regions from stage I by
constructing alignment chains or anchors from short seeds matches. To do this,
we introduce the notion of a kmer mapping graph.

**3\. Extending anchors into alignments using LCS**

> Each anchor reported by GraphMap in stage II represents a shared segment (or
subsequence) between the target and the query sequence with known start and
end positions in both sequences. Due to the presence of repeats, the set of
anchors obtained is not necessarily monotonically increasing in both the
target and query coordinates. For this reason, a subset of anchors that
satisfy the monotonicity condition needs to be selected. The problem of
identifying such a subset can be expressed as finding the Longest Common
Subsequence in k Length Substrings (LCSk).

**4\. Refinining alignments using L1 linear regression**

This step takes care of hits to repetitive regions.

**5\. Construction of final alignment**

> After all selected regions have been processed, they are sorted by the 4
parameter. The region with the highest value 4 is selected for the final
alignment.

The code is [available from github](https://github.com/isovic/graphmap) under
MIT license.

\--------------------------------------

The abstract is posted below.

> Exploiting the power of nanopore sequencing requires the development of new
bioinformatics approaches to deal with its specific error characteristics. We
present the first nanopore read mapper (GraphMap) that uses a read-funneling
paradigm to robustly handle variable error rates and fast graph traversal to
align long reads with speed and very high precision (>95%). Evaluation on
MinION sequencing datasets against short and long-read mappers indicates that
GraphMap increases mapping sensitivity by at least 15-80%. GraphMap alignments
are the first to demonstrate consensus calling with <1 error in 100,000 bases,
variant calling on the human genome with 76% improvement in sensitivity over
the next best mapper (BWAMEM), precise detection of structural variants from
100bp to 4kbp in length and species and strain-specific identification of
pathogens using MinION reads. GraphMap is available open source under the MIT
license at https://github.com/isovic/graphmap.

