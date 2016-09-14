---
title: Genome Reassembly with High-throughput Sequencing Data
tags: []
categories:
- blog
---
Readers may take a look at [an interesting genome assembly
paper](http://www.biomedcentral.com/1471-2164/14/S1/S8) that came out in BMC
Genomics. (h/t: @lexnederbragt @genetics_blog)
<!--more-->

From the methods section,

> As an example of how a reference sequence can aid in assembly, consider the
de Bruijn graph of a donor genome "ATAGAGGCAATGAGCGTGGAGTTC" in Figure 1a.
Note that this graph has two possible Eulerian tours, one in which the lower
branch is taken first, and one in which the upper branch is taken first. Only
one of these tours spells the original donor genome, and a de novo assembly
can not distiguish between them. If, however, we are given the reference
sequence "ATAGCAATCGTGTTC," then it may be possible to discerne the correct
tour. Figure 1c depicts the original de Bruijn graph augmented with the
reference sequence, represented by red edges. In this new graph, it is now
possible to choose the tour that is most parsimonious with the reference
sequence. Stripping away the red edges that have no parallel blue edge, as
shown in Figure 1d makes this more clear. We can now see that the tour
following the upper branch first touches the reference edges 0, 3, 4, 8, and
11 in sequential order, with novel content in between. This indicates that the
donor genome spelled by this tour represents a donor with only three
insertions relative to the reference. The tour following the lower branch
first touches the reference edges out of order in the sequence 0-8-3-4-11,
indicating three insertions as well as a translocation. By appealing to
parsimony, we can therefore conclude that the tour taking the upper branch
first is the more likely of the two.

With this idea in mind, our method begins by building a graph of the contigs
in the donor sequence. The construction of these contigs is flexible, and they
may be derived from the sequencing reads through either de novo assembly or a
hybrid process using both resequencing and assembly.

At Twitter, @lexnederbragt wondered whether the assembler is similar to Cortex
assembler (covered [here](http://www.homolog.us/blogs/2012/12/12/exploring-
single-sample-snp-and-indel-calling-with-whole-genome-assembly/),
[here](http://www.homolog.us/blogs/2013/01/11/high-throughput-microbial-
population-genomics-using-the-cortex-variation-assembler/) and
[here](http://www.homolog.us/blogs/2013/01/12/working-through-the-code-of-
cortex-variant-assembler/)). Based on cursory reading, it did not seem to us
that two approaches are similar. From a more knowledgeable source(@dzerbino),
we came to know about two other papers, where similar assembly techniques were
discussed.

[Assisted assembly: how to improve a de novo genome assembly by using related
species - Sante Gnerre, Eric S Lander, Kerstin Lindblad-Toh and David B
Jaffe](http://genomebiology.com/2009/10/8/R88)

[Reference-assisted chromosome assembly - Jaebum Kim et
al.](http://www.pnas.org/content/early/2013/01/09/1220349110.abstract)

We have not had enough time to compare the approaches of above papers.
However, the most valid criticism of the original manuscript came from C.
Titus Brown, who pointed out that its assembly algorithm was demonstrated only
on simulated data.

![Capture](http://www.homolog.us/blogs/wp-
content/uploads/2013/02/Capture4-300x64.png)

