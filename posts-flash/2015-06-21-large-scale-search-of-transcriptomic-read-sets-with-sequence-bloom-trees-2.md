---
title: Large-Scale Search of Transcriptomic Read Sets with Sequence Bloom Trees
categories:
- rnaseq
---
Here is today's [computational
paper](http://biorxiv.org/content/early/2015/03/26/017087) to read.
<!--more-->

> Enormous databases of short-read RNA-seq sequencing experiments such as the
NIH Sequence Read Archive (SRA) are now available. However, these collections
remain difficult to use due to the inability to search for a particular
expressed sequence. A natural question is which of these experiments contain
sequences that indicate the expression of a particular sequence such as a gene
isoform, lncRNA, or uORF. However, at present this is a computationally
demanding question at the scale of these databases. We introduce an indexing
scheme, the Sequence Bloom Tree (SBT), to support sequence-based querying of
terabase-scale collections of thousands of short-read sequencing experiments.
We apply SBT to the problem of finding conditions under which query
transcripts are expressed. Our experiments are conducted on a set of 2652
publicly available RNA-seq experiments contained in the NIH for the breast,
blood, and brain tissues, comprising 5 terabytes of sequence. SBTs of this
size can be queried for a 1000 nt sequence in 19 minutes using less than 300
MB of RAM, over 100 times faster than standard usage of SRA-BLAST and 119
times faster than STAR. SBTs allow for fast identification of experiments with
expressed novel isoforms, even if these isoforms were unknown at the time the
SBT was built. We also provide some theoretical guidance about appropriate
parameter selection in SBT and propose a sampling-based scheme for potentially
scaling SBT to even larger collections of files. While SBT can handle any set
of reads, we demonstrate the effectiveness of SBT by searching a large
collection of blood, brain, and breast RNA-seq files for all 214,293 known
human transcripts to identify tissue-specific transcripts. The implementation
used in the experiments below is in C++ and is available as open source at
http://www.cs.cmu.edu/~ckingsf/software/bloomtree.

Readers may also find the following discussion at biorxiv helpful.

Fabian:

> What is the impact of sequencing errors on the ability to identify matches?
It seems to me that the approach as described here does not tolerate any
mismatches in the k-mers. While mismatch tolerance can be added in various
ways (post-filtering, multi-queries to account for all possible mismatches, or
reducing the proportion of k-mers that must match along the query), such
changes will certainly impact the performance of the method. This is important
because the approaches used as baseline in the benchmark both are able to
tolerate differences between the query and the sequenced in the index. When
this ability is built on top of SBT, I wonder how seriously will the
performance advantage reduced?

Rob Patro:

> Hi Fabien,

First, I'd like to point out that while I'm not one of the authors of this
paper, I was previously a member of Carl's (the senior author's) group. My
remark regarding your question is that the SBT search procedure, as described
in the current manuscript, views the sequence search as a k-mer subset search
in the tree. Thus, while it's true that a given k-mer must match or not in
it's entirety (i.e. the current search procedure doesn't consider mutating
k-mers to find potential neighbors as matches in sequence space), this
behavior is approximated by the query threshold. If I have a search pattern of
a particular length l, it consists of l-k+1 separate k-mers. The SBT allows
you to specify a threshold concerning how many of the k-mers must be
discovered before a hit is reported. Note, they present results in the
manuscript over a number of thresholds (the parameter Theta) varying from 0.5
to 1. Thus, it's not the case that one would expect sequences with a small
number of edits from the query to be missed. The assumption, of course, is
that the query itself is on a string of length l with l > k. If you're
searching for just a single k-mer, then your point, of course, make sense. The
other difficulty of searching read datasets with other, more traditional
approaches (e.g. a read mapper) is that often times, our query will not exist
in assembled form in the corpus. For example, if I'm searching for a given
transcript in my database, then, clearly, no single read will contain a
sizable fraction of my query (assuming, of course, these aren't PacBio or
Nanopore reads!). Thus, the search problem itself is a bit different than the
normal process of searching for a short sequence in a database of
significantly longer reference sequences. Here, the more common mode of
operation seems to be search for datasets that likely contain sequence (i.e.
reads) drawn from your query of interest (e.g. a target transcript).

