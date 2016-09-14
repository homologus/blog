---
title: SOAPdenovo2 Demystified - A Rough Guideline of Functionality
tags: []
categories:
- blog
---
The next few SOAPdenovo-related commentaries will dig deeper into data
structure and algorithm of SOAPdenovo2. Here is a rough guideline of what to
expect.
<!--more-->

A new user, who likes to stay completely oblivious to the details of how
SOAPdenovo2 works, has the following mental picture of the assembler -

![write-blog](http://www.homolog.us/blogs/wp-content/uploads/2013/02/write-
blog-150x150.png)

Once you get somewhat familiar with the manual, you will find that the
blackbox consists of four independent stages -

![write-blog](http://www.homolog.us/blogs/wp-content/uploads/2013/02/write-
blog1-150x150.png)

Why do we call them independent? The answer will be clear from the following
picture -

![write-blog](http://www.homolog.us/blogs/wp-content/uploads/2013/02/write-
blog2-150x150.png)

Each stage of the program generates a set of output files, and the next stage
reads them as input and does the next step of assembly. So, if you replace the
output of a stage by files generated from a different program (say Velvet or
Minia), SOAPdenovo2 will not be able to tell the difference and run to
completion. That could be an interesting way to mix-and-match various assembly
program.

More adventurous bioinformaticians will probably look into the code and see
what the program does to go from one stage to another. You will find that the
stages run through following functions.

\--------------

pregraph stage:

`

prlRead2HashTable - _parallel code for loading read libraries and splitting
into kmers_

singleKmer

chopKmer4read - _Chops the reads into kmers and store them in KmerSets_

thread_mark

thread_delow - _Removes the kmers with low coverage_

Mark1in1outNode - _Marks the linear kmers_

deLowCov - _Removes the kmers with low coverage_

removeSingleTips - _single tips are removed_

removeMinorTips - _minor tips are removed_

kmer2edges - _Builds edges by combining linear kmers_

prlRead2edge - _parallel code for remapping reads on to edges_

searchKmer

chopKmer4read

parse1read

search1kmerPlus

thread_add1preArc

`

\--------------------

contig stage:

`

swapedge

sortedge

freshArc

solveReps

removeWeakEdges

removeLowCovEdges

cutTipsInGraph

Iterate

createFilter

buildGraphHash

addArc

getUnlikeArc - _get arcs that could be processed incorrectly_

deleteUnlikeArc - _delete this arcs_

freshArc

removeWeakEdges2

removeLowCovEdges2

cutTipsInGraph2

`

\--------------------

map stage:

`

prlContig2nodes

prlLongRead2Ctg

prlRead2Ctg

`

\--------------------

scaffold stage:

`

PE2Links - _Updates connections between contigs based on alignment information
of paired-end reads_

Links2Scaf - _Constructs scaffolds based on alignment information_

scaffolding

`

In our blog, we posted many commentaries on building and resolving de Bruijn
graphs and readers can understand the first three stages by going through
them. The scaffold stage is novel (and quite elaborate) for SOAPdenovo. It
will take us some time to go through the algorithm, but curious readers may
find the following diagram helpful. It explains Links2Scaf function. Functions
in red have many sub-functions not shown in the chart, whereas functions in
black have few sub-functions.

![write-blog](http://www.homolog.us/blogs/wp-content/uploads/2013/02/write-
blog3-150x150.png)

