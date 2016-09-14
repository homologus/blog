---
title: Velvet Optimizer and MetaVelvet
tags:
- velvet
- metagenome
categories:
- blog
---
Researchers using Velvet for genome assembly encounter the problem of which
k-mer size to use to get the best genome assembly. [Velvet
Optimizer](http://bioinformatics.net.au/software.velvetoptimiser.shtml) is a
freely available multi-threaded perl script that runs multiple velveth and
velvetg steps to find optimal Velvet parameters for a library of reads. It was
originally written by Simon Gladman of Commonwealth Scientific and Industrial
Research Organisation in Australia.
<!--more-->

The commands to run 'velvetoptimizer' are explaind in [this
thread](http://umbc.rnet.missouri.edu/resources/How2RunVELVETonClark.html). If
we find other links, they will be reported here.

\-----------------------

Tsuyoshi Hachiya and his colleagues from Keio university wrote a [modified
version](http://metavelvet.dna.bio.keio.ac.jp/) of Velvet for assembling
metagenomes. They used a partitioning step to partition the de Bruijn graph of
all reads, and then assembled each partition independently.

We previously commented that metagenomes and transcriptomes have many
similarities. Conceptually, their approach indeed appears similar to Trinity,
but I have not checked the details.

\-----------------------

We are going through the Velvet and Oases mailing lists of the last three
years to find useful ideas for genome/transcriptome assembly. Several very
smart and experienced researchers comment there from time to time. We plan to
use these [Velvet](http://www.homolog.us/smf/index.php?topic=60.0) and
[Oases](http://www.homolog.us/smf/index.php?topic=61.0) threads of our forum
to report what we find, and once done, we plan to write a full blog post
summarizing all ideas. The mailing lists have almost thousand posts and it is
taking us some time to go through them all. If you like, please feel free to
add.

