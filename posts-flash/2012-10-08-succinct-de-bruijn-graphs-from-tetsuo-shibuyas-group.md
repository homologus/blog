---
title: Succinct de Bruijn Graphs from Tetsuo Shibuya's Group
tags: []
categories:
- blog
---
Reader Lo kindly forwarded us the paper titled [Succinct de Bruijn
Graphs](http://link.springer.com/chapter/10.1007/978-3-642-33122-0_18) by
Alexander Bowe, Taku Onodera, Kunihiko Sadakane, and Tetsuo Shibuya and kept
us busy over the weekend. When we covered [Arapan-S paper from the same group
few weeks back](http://www.homolog.us/blogs/2012/09/24/cope-for-joining-pe-
reads-and-arapan-s-for-small-genomes/), we did not take them too seriously.
After all, who wants to solve viral genomes, when we have mammalian genomes
and metagenomes to take care of? However, their current paper suggests that
they definitely deserve a [place in our NGS innovation
map](http://www.homolog.us/blogs/2012/08/16/where-are-innovative-ngs-
algorithms-coming-from/).
<!--more-->

**Search for Low Memory Assembler**

If you have been following our commentaries over the last few months, you know
that computer scientists are up in arms to solve an important problem
regarding NGS genome assembly, namely how to do it with less RAM. Unlike large
genome centers, most computer scientists do not have sugar-daddies to buy them
512GB RAM computers. They are compelled to find low-memory alternatives for
assembling genomes, so that they can stay in the game without going broke.

To quickly recap, here are few proposed alternatives by various groups.

1\. [Gossamer from Conway and Bromage](http://www.homolog.us/blogs/2012/06/17
/succinct-data-structure/): T. C. Conway and Andrew Bromage from NICTA,
Australia asked the theoretical question of how little RAM a de Bruijn graph
would need, if they wanted to store all node and edge information? They came
up with roughly 30.7 GB for human genome (22 bits/edge), and implemented their
ideas in Gossamer assembler.

2\. [SparseAssembler](http://www.ncbi.nlm.nih.gov/pmc/articles/PMC3369186/):
Ye et al. showed that it was possible to do assembly without storing all
nodes, and demonstrated their ideas in their SparseAssembler implementation.
Recently released [SOAPdenovo2
assembler](http://www.homolog.us/blogs/2012/06/27/testing-soapdenovo2/) comes
with a pregraph module that likely implements ideas similar to
SparseAssembler.

3\. [Minia from Chikhi and Rizk](http://www.homolog.us/blogs/2012/10/01/minia-
assembly-algorithm-and-french-revolution/): Rayan Chikhi of INRIA, France
decided to implement Bloom filter data structure and save only the nodes, not
edges, to cut memory requirement lot further than theoretical limit of
Conway/Bromage.

4\. [Meraculous](http://www.homolog.us/blogs/2012/10/02/perfect-hash-
algorithm-of-meraculous-assembler/) (also discussed
[here](http://www.homolog.us/blogs/2012/08/16/genome-assembly-mermaid-and-
meraculous/)): Meraculous algorithm from JGI was similar to Rayan's Minia
regarding its decision to store only the nodes. However, instead of Bloom
filter, they stored their nodes in a structure called perfect hash. As Rayan
explained in [comment section](http://www.homolog.us/blogs/2012/10/02/perfect-
hash-algorithm-of-meraculous-assembler/), their memory usage was 21.6
bits/k-mer, or close to Conway/Bromage limit.

5\. [String Graph Assembler from Simpson and
Durbin](http://www.homolog.us/blogs/2012/02/11/string-graph-assembler/) (also
check [here](http://www.homolog.us/blogs/2012/02/13/string-graph-
of-a-genome/)): Simpson and Durbin decided to part with de Bruijn graph
altogether and implemented string graph assembler to significantly reduce
memory usage. String graph assembler is close to overlap-layout-consensus
method for assembly, but the biggest contribution of Simpson/Durbin was to
figure out a way to use Burrows Wheeler transform to reduce time requirement
for finding the overlaps.

**Alex Bowe's Succinct de Bruijn Graphs**

The succint de Bruijn graph structure proposed by Bowe _et al._ reduces memory
requirement significantly from the derived theoretical limit of
Conway/Bromage, while storing all the edges of de Bruijn graph. From their
paper:

> For example, the succinct representation of Conway and Bromage [5] uses
40.8GB for storing a de Bruijn graph with m =12,292,819,311 edges and k = 27
(28.5 bits per edge). On the other hand, if we use an efficient implementation
of rank/select data structures [17] for our representation, the estimated size
is less than 5 bits per edge. Therefore the above graph is stored in less than
8GB.

How do they do that? They figured out a way to perform [Burrows Wheeler
transform](http://www.homolog.us/blogs/2011/10/03/finding-us-in-homolog-us/)
on the nodes/edges of a de Bruijn graph and store the graph in compressed
manner, while being able to access the nodes rapidly. In their paper, they
presented an example of a de Bruijn graph of three reads in Fig. 1 and
explained how it looked in compressed form in Fig. 2. They also provide sample
code for their compression algorithm [here](http://code.google.com/p/csalib/).
The code comprises of only one 500 line long C-program sdg.c that compiles
very easily.

Enjoy !!

