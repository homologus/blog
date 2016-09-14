---
title: Quick Update on Pacbio and DALIGNER - Jared Simpson's GFA Module
tags: []
categories:
- blog
---
Jared Simpson posted -
<!--more-->

![Capture](http://www.homolog.us/blogs/wp-content/uploads/2014/11/Capture-
300x74.png)

He added a new module to DALIGNER to get the output in Graphical Fragment
Assembly format (explained below). The code is [here
](https://github.com/jts/DALIGNER/blob/master/LA2gfa.c)and the README file is
[here](https://github.com/jts/DALIGNER/blob/master/README#L251).

> 9\. LA2gfa [-a:]

Write the overlaps and containments found by daligner in Graphical Fragment
Assembly

(gfa) format. This textual output is quite large due to the long CIGAR strings
but

is suitable for small assembly projects and useful for prototyping algorithms.

Example:

// Recall G.db from the example in DAZZ_DB/README

\-------------------------------------------

What is GFA or Graphical Fragment Assembly format? It is an attempt to
standardize the output of assembly programs so that different assemblers can
talk to each other. Heng Li argued that the original proposal of FASTG was
mathematically incorrect ('The critical problem with FASTG is that it puts
sequneces on arcs/edges. It is unable to describe a simple topology such as
A->B; C->B; C->D without adding a dummy node, which breaks the theoretical
elegance of assembly graphs. '), and proposed a a more correct approach.

Readers may check the relevant post from Heng Li's blog.

[A proposal of the Grapical Fragment Assembly
format](http://lh3.github.io/2014/07/19/a-proposal-of-the-grapical-fragment-
assembly-format/)

> Introduction

Almost three years ago, there was a lengthy discussion in the Assemblathon
mailing list about a generic format for fragment assemmbly. The end product is
the FASTG format. In the discussion, I have expressed several major concerns
with the format. The top one is that it is mathematically wrong. Three years
later, FASTG is still not widely used. At this point, Adam Phillippy and Pall
Melsted openly called for a generic assembly format again. I also feel the
pressing necessity of standardization, so decided to give a try myself. This
is the Graphical Fragment Assembly format, or GFA in abbreviation.

In this post, I will start from the theoretical basis of assembly graph,
describe the format and finally discuss the potential issues with the
proposal.

I showed an earlier version of this format to Richard Durbin, Daniel Zerbino
and Benedict Paten last night in Oxford. That version was a variant of FASTA.
When I was formalizing the format in this post, I found FASTA is too crowded
and too limited. Following the suggestion of Daniel, I finally adopted a
format similar to ASQG and the PSMC output.

Theory

DNA sequence assembly is often (though not always) represented as a graph.
There are multiple types of graphs including de Bruijn graph, overlap graph,
unitig graph and string graph. They are all birected graph. Briefly, in this
graph, each vertex is a sequence and each arc is an overlap. Because DNA
sequences have two strands, an arc may have four directions, representing the
four possible overlaps: forward-forward, forward-reverse, reverse-forward and
reverse-reverse. It should be noted that a k-mer de Bruijn graph is equivalent
to an overlap graph for k-mer reads with (k-1)-mer overlaps. It is a
bidirected graph, too.

The critical problem with FASTG is that it puts sequneces on arcs/edges. It is
unable to describe a simple topology such as A->B; C->B; C->D without adding a
dummy node, which breaks the theoretical elegance of assembly graphs. Due to
the historical confusion between vertices and edges, I will avoid using these
terminologies. I will use a segment for a piece of sequence and a link for a
connection between segments.

The GFA format

Although we can describe an assembly graph with bidirected arcs, I find in
practice, it is easier and more explicit to describe links between the ends of
segments. Gene Myers took a similar approach in his string graph paper. Based
on this observation, I uniquely label the 5-end and the 3-end of each segment.
The following shows an assembly graph with seven segments in GFA:

\------------------------------------------------------------------------

Speaking of Pacbio bioinformatics, here are a set of major developments -

[Very Efficient Hybrid Assembler for PacBio
Data](http://www.homolog.us/blogs/blog/2014/10/13/very-efficient-hybrid-
assembler-for-pacbio-data/)

[After HGAP And SPAdes Comes New PacBio Assembler
MHAP](http://www.homolog.us/blogs/blog/2014/08/15/after-hgap-and-spades-comes-
new-pacbio-assembler-mhap/)

[In DALIGN Paper, Gene Myers Delivers a Major Blow to His Biggest
Competitor](http://www.homolog.us/blogs/blog/2014/07/28/in-dalign-paper-gene-
myers-delivers-a-major-blow-to-his-biggest-competitor/)

