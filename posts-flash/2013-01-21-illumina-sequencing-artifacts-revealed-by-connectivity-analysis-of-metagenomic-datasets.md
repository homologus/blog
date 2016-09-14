---
title: Illumina Sequencing Artifacts Revealed by Connectivity Analysis of Metagenomic
  Datasets
tags: []
categories:
- blog
---
[Here](http://arxiv.org/abs/1212.0159) is a very interesting article by C.
Titus Brown's group. It uses connectivity analysis of graphs to find artifacts
in sequencing libraries.
<!--more-->

>

Sequencing errors and biases in metagenomic datasets affect coverage-based
assemblies and are often ignored during analysis. Here, we analyze read
connectivity in metagenomes and identify the presence of problematic and
likely a-biological connectivity within metagenome assembly graphs.
Specifically, we identify highly connected sequences which join a large
proportion of reads within each real metagenome. These sequences show
position-specific bias in shotgun reads, suggestive of sequencing artifacts,
and are only minimally incorporated into contigs by assembly. The removal of
these sequences prior to assembly results in similar assembly content for most
metagenomes and enables the use of graph partitioning to decrease assembly
memory and time requirements.

Sorry for late reporting. The paper had been posted at arxiv site for over a
month back. We got somewhat turned off about artifact papers having [written
one several years
back](http://www.febsletters.org/article/S0014-5793%2807%2900681-3/abstract).
In our paper, we used sequence statistics to find an artifact in microarray
data, and then traced back its chemical origin. We thought it was very cool
finding and were very excited about it, but nobody else cared :(

