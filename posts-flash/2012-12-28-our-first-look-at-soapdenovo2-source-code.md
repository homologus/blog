---
title: Our First Look at SOAPdenovo2 Source Code
tags: []
categories:
- blog
---
Here is today's good news !! Reader [Scott Edmunds informed
us](http://www.homolog.us/blogs/2012/12/27/should-soapdenovo2-source-code-be-
made-public/) that BGI uploaded [SOAPdenovo2 code to
Sourceforge](http://sourceforge.net/projects/soapdenovo2/). We downloaded the
tar.gz file to our server and it nicely expanded into two folders with
sparsePregraph and standardPregraph codes.
<!--more-->

The difference between those two versions is in the manner by which the de
Bruijn graphs are constructed. Full points go to Rayan Chikhi [for correctly
guessing](http://www.homolog.us/blogs/2012/07/04/testing-soapdenovo2-pre-
release-version-part-ii/) their approach. Standard Pregraph version of
SOAPdenovo2 includes all k-mers to construct a full de Bruijn graph, and
therefore requires tons of memory. Sparse Pregraph version implements an
approximate method described in [this
paper](http://www.biomedcentral.com/1471-2105/13/S6/S1/). The approach uses
sparseness of de Bruijn graph and requires lot less memory, but can introduce
some errors in assembly. Another difference - standardPregraph version was
written in C, and sparsePregraph version was written in C++. That is probably
why they were split into two folder.

The 'make' command ran properly in each folder after we manually modified the
location of gcc in Makefile, and also removed the condition that only gcc
4.5.0 or above could be used. We are not sure what bad effect gcc 4.4.5 would
have, but at least all source codes compiled without any problem.

Total number of lines of C codes in Standard Pregraph directory is ~40,000,
and the codes are split into 50 C files. Here are their brief descriptions.

**main.c (557 lines) **

\- Main program. It processes input options, and invokes various other
functions (call_pregraph, call_heavygraph, call_align,
<del>call_map2contig,</del> and call_scaffold) to assemble a genome.

**_Step 1. (constructing pregraph)_**

**pregraph.c (229 lines )**

\- Constructs pregraph. From BGI's description -

> The main function for pregraph step. its processes are as below:

1\. Builds the kmer hash sets and remove the low coverage kmers.

2\. Removes the tips which length are no greater than 2*K.

3\. Builds edges by combining linear kmers.

4\. Maps the reads back to edges and build preArcs (the connection between
edges).

Related:

**cutTipPreGraph.c (639 lines )**

**output_pregraph.c (112 lines )**

**_Step 2. (building contigs)_**

**contig.c (319 lines )**

Constructs contigs.

> Description:

The main function for contig step . its processes are as below:

1\. Solve repeat

2\. Merge bubble(clean bubble is optional for multikmer)

3\. Remove weak edge and low coverage edge

4\. Cut tips

5\. Iterate multikmer(optional)

Related:

**output_contig.c (432 lines )**

**iterate.c (2510 lines )**

**compactEdge.c (142 lines )**

**concatenateEdge.c (335 lines )**

**linearEdge.c (429 lines )**

**cutTip_graph.c (576 lines )**

**cutTip_graph2.c (500 lines )**

**bubble.c (2466 lines )**

**loadPath.c (336 lines )**

**_Step 3. (mapping)_**

**map.c (227 lines )**

Maps reads onto contigs in the following manner (check call_align function).

>

Description:

This is the main function for map step. It includes the following steps:

1.Chops contig (>=k+2) into kmer sets, marks the kmer occured twice or more as
deleted,

records the unique kmers related contig's id and the position of the kmer on
the contig.

2.Maps reads to edges.

Related:

**prlHashCtg.c (459 lines )**

**prlRead2Ctg.c (1280 lines )**

**_Step 4. (Scaffolding)_**

**scaffold.c (233 lines )**

Builds scaffolds.

> This is the main function of 'scaff' step. It includes the following steps:

1\. Reads required input information.

2\. Constructs scaffolds.

3\. Fills gaps if required, then output result.

Related:

**output_scaffold.c (100 lines )**

**read2scaf.c (327 lines )**

**orderContig.c (8786 lines )**

**connect.c (227 lines )**

**searchPath.c (253 lines )**

**loadGraph.c (669 lines )**

**localAsm.c (2375 lines )**

**prlReadFillGap.c (1937 lines )**

**5\. _Implementation of Useful Tasks_**

**seq.c (254 lines )**

Converts sequences to bytes, and does other useful tasks.

**darray.c (89 lines )**

Creates a dynamic array.

**readInterval.c (77 lines )**

Allocated memory for bubble.c.

**dfibHeap.c (99 lines )**

**fibHeap.c (77 lines )**

Adds node to a heap.

**dfib.c (594 lines )**

**fib.c (709 lines )**

Came from Velvet.

**mem_manager.c (102 lines )**

Memory manager.

**stack.c (165 lines )**

**hashFunction.c (155 lines )**

**kmerhash.c (540 lines )**

**lib.c (627 lines )**

**check.c (132 lines )**

**kmer.c (842 lines )**

**newhash.c (705 lines )**

**6\. _Unassigned code_**

We will continue to modify the following sections, as we work through the
code.

**arc.c (350 lines )**

**read2edge.c (1612 lines )**

**prlRead2path.c (1334 lines )**

**readseq1by1.c (1242 lines )**

**prlHashReads.c (1030 lines )**

**loadPreGraph.c (698 lines )**

**attachPEinfo.c (678 lines )**

**node2edge.c (649 lines )**

**splitReps.c (634 lines )**

Updated Figure (1/5/2013):

Please note some changes from above.

![write-blog](http://www.homolog.us/blogs/wp-content/uploads/2013/01/write-
blog.png)

