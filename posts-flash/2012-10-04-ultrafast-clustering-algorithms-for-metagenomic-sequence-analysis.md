---
title: Ultrafast Clustering Algorithms for Metagenomic Sequence Analysis
tags: []
categories:
- blog
---
If you are looking for programs to cluster sequences, a [paper published in
Briefings in Bioinformatics in
July](http://bib.oxfordjournals.org/content/early/2012/07/06/bib.bbs035.full)
describes several options. Although it is motivated by metagenomics, the
programs are generally useful for all other genomics problems.
<!--more-->

>

Sequence clustering is not a new topic; it existed long before the emerging of
metagenomics and NGS technologies. In the past, many available clustering
programs were used for clustering protein sequences such as ProtoMap [18],
ProtoNet [19], RSDB [20], GeneRAGE [21], TribeMCL [22], ProClust [23],
UniqueProt [24], OrthMCL [25], MC-UPGMA [26], Blastclust [27] and CD-HIT
[2831]. Many methods were also used for clustering expressed sequence tags
(ESTs), such as Unigene [32], TIGR Gene Indices [33], d2_cluster [34] and
several others [3537].

Many of the above clustering methods require all against all comparisons of
sequences for optimal results, so they are very computational intensive for
large data sets. A method for reducing the intensive requirement arose with
CD-HIT. Thus, with the rapid growth of sequence data, the fast program CD-HIT
become a very popular clustering tool; it has been widely used in many areas
such as preparing NR reference databases [38]. CD-HIT uses a greedy
incremental algorithm. Basically, sequences are first ordered by decreasing
length, and the longest one becomes the seed of the first cluster. Then, each
remaining sequence is compared with existing seeds. If the similarity with any
seed meets a pre-defined cutoff, it is grouped into that cluster; otherwise,
it becomes the seed of a new cluster. More recently, several new fast
programs, including Uclust [39], DNACLUST [40] and SEED [41], have been
developed using greedy incremental approaches similar to that introduced by
CD-HIT. These methods use various heuristics and achieved high speed in
clustering NGS sequences. Herein, we briefly introduce the features and
functions of these programs.

