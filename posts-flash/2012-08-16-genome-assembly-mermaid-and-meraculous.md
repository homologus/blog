---
title: Genome Assembly - MERmaid and Meraculous
tags: []
categories:
- blog
---
We will discuss two papers that are being included in our list of [NGS-related
publications on Genome
Assembly](http://www.homolog.us/blogs/2012/08/07/building-a-ngs-reference-
list-please-add/) \-
<!--more-->

[MERmaid: A Parallel Genome Assembler for the Cloud](http://www.cs.berkeley.ed
u/~kubitron/courses/cs252-S12/projects/reports/project1_report.pdf) [a CS
course project at Berkeley] hat tip [Kevin's GATTACA blog](http://kevin-
gattaca.blogspot.com/2012/08/mermaid-parallel-genome-assembler-for.html)

and

[Meraculous: De Novo Genome Assembly with Short Paired-End Reads](http://www.p
losone.org/article/info%3Adoi%2F10.1371%2Fjournal.pone.0023501) [Published in
PLoS ONE]

The first paper presents a cutting edge project to implement a highly
parallelized version of second paper's algorithm. So, let us start our
discussion with the second one.

Meraculous is JGI's arrival into the NGS scene. We were wondering, why they
presented a de Bruijn assembler in 2011 given that Velvet and ABySS were out
for a while, and JGI had unlimited funding. The answer was found here.

![](http://www.homolog.us/blogs/wp-content/uploads/2012/08/JGI-300x39.png)

Danny Rokhsar's team likely had difficult questions to answer given Steven
Salzberg's group is an expert in NGS bioinformatics.

**What is new in meraculous?**

> 1\. Unlike other short-read assemblers, meraculous avoids an explicit error
correction step, instead relying on base quality scores.

2\. Meraculous also incorporates a novel low-memory hash structure to access
the deBruijn graph, allowing a small memory footprint compared with other
short-read assemblers.

3\. Many stages of the meraculous algorithm are parallelized, and to document
their scalability we........show that for mammalian genomes the limiting
memory structure requires less than 10 Gb of RAM.

The first point should be reasonably clear for anyone working on sequence
data. Let us explain the second and third ones in more detail.

How does Meraculous dramatically reduce its memory footprint? It uses a
'perfect hash'. Usual implementation of hash tables is dynamic, where the
potential entries are not known before hand. That means a predetermined hash
function takes care of all kinds of assemblies, and the memory allocation
keeps provision for potential collisions.

If the entries going into a hash table are known before hand and the hash
function is chosen dynamically based on potential entries, it is possible to
design a hash function for each problem that minimizes collision.

How are the entries known before hand? Real simple. Genome assembly is done
from short reads and the reads can be processed to find the complete set of
k-mers. Among those, the k-mers present only once or twice are potentially due
to noise and k-mers present multiple times are real. [We have been through
this point many times in our earlier
discussions](http://www.homolog.us/blogs/2011/09/20/maximizing-utility-of-
available-rams-in-k-mer-world/). Bloom filter is another way of cutting bad
k-mers.

**What is new in MERmaid?**

> 1\. While MERmaid follows the general workflow of existing assemblers,
especially

that of Meraculous [7], it makes several important contributions. Chief among
these is accessbility. MERmaid is open-source and was designed to be run on
commodity clusters rather than supercomputers.

2\. MERmaid employs lowmemory Bloom filters to store data that is likely to be

erroneous.

3\. Other contributions include the use of locality sensitive hashing
functions to improve the locality of distributed data sets and the exploration
various compression schemes for storing data.

4\. We use a scalable Bloom filter in order to dynamically adjust the
capacity.

Our readers possibly do not need any explanation on the above points. So let
us discuss an interesting part of the paper.

**Where are the going next?**

**GPU**: "We plan to implement GPU versions of those specific kernels." 

**Preprocessor for optimal parameters**: "Plans are also underway to develop a preprocessing engine. This engine would sample the input dataset and determine determine optimal values for various configuration parameters such as dmin, k, Qmin, and the intial size for the Bloom 

filter."

**Fault tolerance**: "Assembly of genomic data often takes a long time, and having a job fail can be frustrating.....Currently, if one job fails for us, then we need to rerun the entire step as our checkpoints are only between steps." 

**Importance of above papers**

The readers may argue that the above papers do not have any algorithm that is
spectacularly different from what we discussed here over the last year. The
last section is our main reason for covering the papers. JGI is a very large
sequencing center and it encounters operational problems not being experienced
by small groups working on one or two genomes. So, by studying what it is
doing, you may gauge, where the technological front is heading to.

