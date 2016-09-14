---
title: PLOS One Paper - "Comparing Memory-Efficient Genome Assemblers on Stand-Alone
  and Cloud Infrastructures"
tags: []
categories:
- blog
---
We seem to have missed a nice [PLOS One paper](http://www.plosone.org/article/
info%3Adoi%2F10.1371%2Fjournal.pone.0075505). (h/t: @rayanchiki) Authors
compared many of the new approaches (e.g. Minia, SGA), which are not yet fully
incorporated in mainstream programs, but can significantly improve
performance. We wish Heng Li's Fermi were included.
<!--more-->

Two take home messages from the abstract:

> 1\. Our experiments prove that it is possible to generate draft assemblies
of reasonable quality on conventional multi-purpose computers with very
limited available memory by choosing suitable assembly methods.

2\. By combining existing methodologies, we propose two general assembly
strategies that can improve short-read assembly approaches and result in
reduction of the memory footprint.

Evaluation details from the paper -

> In this study, we quantify the memory requirements of modern assemblers for
a variety of datasets. We compare the prevalent memory-efficient techniques
against a typical traditional approach (i.e., Velvet [6]). We compare the
following programs: SparseAssembler [24], Gossamer [25], Minia [27] and SGA
[30]. All of them are open-source and representative of the recent assembly
trends, namely: the efficient construction of large assembly graphs with less
memory and the utilization of compressed data structures. Our performance
evaluation follows the gold standard of genome assembly evaluation [18] and is
applied to four well-studied datasets with diverse complexity and sizes,
ranging from a few millions to hundreds of millions of reads. We performed the
experiments on systems with 4 to 196 GB RAM, corresponding to a wide range of
equipment, from laptops to desktops to large servers. We report the memory
requirements for each program and provide directions to researchers for
choosing a suitable execution environment for their assemblies. This is the
first study that offers a practical comparison of memory-efficient assemblers
with respect to the trade-offs between memory requirements, quality of
assembly and execution time.

We also propose two new assembly strategies that combine existing memory-
efficient approaches for each stage of the execution. The first strategy is
Diginorm-MSP-Assembly (DiMA), which uses two pre-processing steps: Diginorm
[28] for data cleaning followed by MSP [29], which distributes the data on
disk partitions. The final assembly step allows for lightweight processing and
any well-known assembler can be used. Our results show that DiMA is a general
strategy for reducing the memory requirements of traditional assemblers. The
combination of DiMA with the Velvet assembler results in better memory
utilization than that by the original Velvet program and is capable of
assembling the B. impatiens genome using about 20 GB RAM, whereas the original
Velvet program would crash because of insufficient memory on a 192 GB server.
The second strategy is Zero-memory assembly (ZeMA), which has a data cleaning
preprocessing phase that uses Diginorm. Afterwards, ZeMA builds a sparse de
Bruijn graph using SparseAssembler. The ZeMA pipeline executed on a
conventional laptop successfully assembles the B. impatiens genome using only
3.2 GB of RAM.

What did they find?

> Our results show that Diginorm-Velvet, SparseAssembler [24], Minia [27] and
Diginorm [28] appear to be among the most useful methods under limited memory
resources.

Regarding the ranking of the performance of the assemblers, we are compelled
to say that the selection of the metrics and the ranking criteria were
somewhat subjective and far from perfect. Thus, the ranking results that we
report should be considered with caution. Based on the selected ranking
procedure Diginorm-Velvet ranks first among the studied programs for two
reasons: (i) Velvet is a very efficient assembler that produces high-quality
results; (ii) when data size and complexity increase, Diginorm reduces the
memory footprint without affecting the accuracy of the results.
SparseAssembler ranks second. SparseAssembler has good trade-offs between
accuracy, wrong assemblies, run-time and memory utilization. Minia ranks third
in our comparison. The quality is slightly lower for smaller datasets and,
surprisingly, the method is optimized for larger genomes like that of the
bumblebee. Minia requires minimal memory and it can be used on conventional
laptops and desktops. DiMA enhances the memory footprint of Velvet for larger
datasets and ranks fourth. However, in-memory loading of a huge assembly graph
remains a bottleneck and restricts the applicability of DiMA. ZeMA ranks
fifth. The low quality that it achieves confirms our initial hypothesis that
data cleaning and sparse creation of DBG lead to the loss of significant
information. However under limited memory, the strategy is able to process
large datasets and produce draft assemblies on a conventional laptop. SGA and
Gossamer work only for the smaller datasets and the quality if the assemblies
is lower compared to those of other programs.

We skipped over the discussions on cloud, because the number of variables were
simply too many to make the comparison meaningful. Moreover, we do not buy
retail and first-hand, when we get a server. So, the laptop and workstation
quotes are not good comparisons. In any case, it is a fairly good paper with
lot to digest.

