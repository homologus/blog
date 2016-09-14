---
title: SOAPdenovo2 on Github, Now 'Searching Soul' on Assemblers
tags: []
categories:
- blog
---
Thanks to Ruibang Luo, Zhenyu Li and Long Xie of BGI, [SOAPdenovo2 code is
available from github](https://github.com/aquaskyline/SOAPdenovo2). We
[created a separate copy](https://github.com/homologus/SOAPdenovo2) and loaded
the modularized directories for pregraph, contig, map and scaffold.
<!--more-->

For those interested in running the code, those are not earthshaking
developments. SOAPdenovo2 code is already modularized and other helpful tools
exist. Rayan Chikhi mentioned in an earlier comment section about a tool named
'prepare' that allows users to mix and match between assembly programs. For
example, you can run the pregraph stage using some other assembler and then
'prepare' the output to use SOAPdenovo for scaffolding.

> Note that there exists a "prepare" tool to convert a set of contigs or
scaffolds (FASTA file) to the input of the "map" step, see
<http://seqanswers.com/wiki/How-to/scaffolding#Example_3:_SOAP>

Our interest in splitting the code is somewhat different. It helps us modify
the code and play with it. After publication of the Assemblathon paper, Nature
news blog reported:

[Genome assembly contest prompts soul-
searching](http://blogs.nature.com/news/2013/07/genome-assembly-contest-
prompts-soul-searching.html)

>

One notable finding from the contest was that different assemblers and the
same assemblers in the hands of different teams did not give consistent
results. That echoes the results of Assemblathon 1, which wrapped up in 2011.
But the problem itself may be more significant now than it was then, owing to
the democratization of genomics, with many more labs now using many more
methods to assemble many more genomes from scratch.

Perhaps because of this, Assemblathon 2 has sparked a bit of soul-searching
among bioinformaticians, who have debated its results and their significance
since a preprint of the paper was posted on arXiv in January.

.....

This isnt an ideal situation for the average scientist who just wants to know
which is the best tool to use for a specific project. On the blog Haldanes
Sieve, Bradnam compares the process of selecting an assembly method to that of
choosing the best pizzeria in Davis.

[T]he notion of a best pizza is highly subjective and the best pizza for one
person is almost certainly not going to be the best pizza for someone else,
Bradnam writes.

We like to do the soul-searching in following manner. We will ask - 'by making
what set of changes to the code of an assembly program can we turn it into
another assembly program?' Each assembly program works on the same set of
reads, creates a giant graph and simplifies it into the contig assembly. Then
another graph is created and resolved into the scaffold assembly. Therefore,
the differences between the programs are usually from the heuristics and
algorithms. We are novices and like to learn about what causes the
differences,

We will start with SOAPdenovo2 pregraph+contig and Minia and run both of them
on the an error-corrected _E. coli_ data set and then on a fish library. We
will try to play with the code to see whether it is possible to go from one
output to another (except for the fact that SOAPdenovo keeps the read counts
and Minia does not).

