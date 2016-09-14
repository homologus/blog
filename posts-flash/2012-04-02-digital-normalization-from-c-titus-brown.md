---
title: Digital Normalization from C. Titus Brown
tags: []
categories:
- blog
---
For new readers, easiest way to follow us is through our [twitter
feed](https://twitter.com/#!/homolog_us/). The feed is updated, whenever we
post a commentary here.
<!--more-->

From time to time, [we referenced](http://www.homolog.us/blogs/2011/08/10
/large-computer-distributed-cluster-or-amazon-cloud/) commentaries from
professor C. Titus Brown of Michigan State University, who writes [an
informative blog](http://ivory.idyll.org/blog/) on next-gen sequencing
algorithms. Today I received a ping from him in our comment section about
'digital normalization' for data reduction that their group is ready to
publish. This approach is important for anyone trying to cope with large
volume of next-gen data and likes to reduce the data without losing any useful
information.

Here is the abstract of their paper -

> Deep shotgun sequencing and analysis of genomes, transcriptomes, amplified
single-cell genomes, and metagenomes enable the sensitive investigation of a
wide range of biological phenomena. However, it is increasingly difficult to
deal with the volume of data emerging from deep short-read sequencers, in part
because of random and systematic sampling variation as well as a high
sequencing error rate. These challenges have led to the development of entire
new classes of short-read mapping tools, as well as new de novo assemblers.
Even newer assembly strategies for dealing with transcriptomes, single-cell
genomes, and metagenomes have also emerged. Despite these advances, algorithms
and compute capacity continue to be challenged by the continued improvements
in sequencing technology throughput. We here describe an approach we term
digital normalization, a single-pass computational algorithm that discards
redundant data and both sampling variation and the number of errors present in
deep sequencing data sets. Digital normalization substantially reduces the
size of data sets and accordingly decreases the memory and time requirements
for de novo sequence assembly, all without significantly impacting content of
the generated contigs. In doing so, it converts high random coverage to low
systematic coverage. Digital normalization is an effective and efficient
approach to normalizing coverage, removing errors, and reducing data set size
for shotgun sequencing data sets. It is particularly useful for reducing the
compute requirements for de novo sequence assembly. We demonstrate this for
the assembly of microbial genomes, amplified single-cell genomic data, and
transcriptomic data. The software is freely available for use and
modification.

The paper is actually published as far as I am concerned, because it is
available from [arxiv.org](http://arxiv.org/abs/1203.4802) and [his
website](http://ivory.idyll.org/blog/mar-12/diginorm-paper-posted.html). Titus
has been writing about his work in bits and pieces in his blog over the last
18 months. So, regular readers of his blog are 12-18 months ahead of journal
readers about his cutting-edge research.

