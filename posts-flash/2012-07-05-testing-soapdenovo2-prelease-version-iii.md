---
title: Testing SOAPdenovo2 Prelease Version - III
tags:
- SOAPdenovo
categories:
- blog
---
This commentary is a continuation of [previous
one](http://www.homolog.us/blogs/2012/07/04/testing-soapdenovo2-pre-release-
version-part-ii/). We are adding some additional information in case you want
to explore the pregraph module further.
<!--more-->

Here is the full set of input parameters for the sparse pregraph module -

> USAGE:

pregraph_sparse -s readsInfoFile -K kmer -z GenomeSize[-g MaxKmerEdgeLength -d
KmerFreqCutoff -e KmerEdgeFreqCutoff -r run_mode -p n_cpu] -o OutputFile

-s readsInfoFile: The file contains information of solexa reads 

-K kmer : k value in kmer 

-g MaxKmerEdgeLength(default 15): number of skipped intermediate kmers, support 1-25. 

-z GenomeSize(required): estimated genome size 

-d KmerFreqCutoff(optional): delete kmers with frequency no larger than (default 1) 

-e KmerEdgeFreqCutoff(optional): delete kmers' related edge with frequency no larger than (default 1) 

-r run mode(default 0): 0 build graph & build edge and preArc, 1 load graph by prefix & build edge and preArc, 2 only build graph 

-p n_cpu(default 8): number of cpu for use 

-o OutputFile: prefix of output file name

Reader Rayan pointed out that the module is most likely implementing the
method presented [in this
paper](http://www.biomedcentral.com/1471-2105/13/S6/S1/). We believe he is
right based on our understanding of the communications with BGI team. With the
suggested method, you can change the amount of RAM needed by adjusting the
'-g' parameter (number of skipped intermediate kmers). If the parameter is set
as 1 (1 intermediate kmer skipped), no savings in RAM usage will be seen.

Here are two relevant snippets from the paper, describing the method and what
it can achieve -

> In this paper, we demonstrate that constructing a sparse assembly graph
which stores only a small fraction of the observed k-mers as nodes and the
links between these nodes allows the de novo assembly of even moderately-sized
genomes (~500 M) on a typical laptop computer.

>

Specifically, instead of storing every single k-mer (in a de Bruijn graph) or
read (in an overlap graph) as nodes, we store a sparse subset of these nodes
while still ensuring the assembly can be performed. Here, we demonstrate that
this approach greatly reduces computational memory demands without sacrificing
the accuracy of assembly.

