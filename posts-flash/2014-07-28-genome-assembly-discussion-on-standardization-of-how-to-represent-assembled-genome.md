---
title: Genome Assembly - Discussion on Standardization of How to Represent Assembled
  'Genome'
tags: []
categories:
- blog
---
A few days back, Heng Li opened up a new discussion on -
<!--more-->

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

Also, a follow up post is here -

[First update on GFA](http://lh3.github.io/2014/07/23/first-update-on-gfa/)

> I was out of the town in the past few days, so have not been able to focus
on GFA. Now I am back to work to give the first update on the format based on
the comments from many people, which I appreciate a lot.

In comparison to my initial proposal, the first and the major change is to
name segments instead of the ends of segments. This seems the consensus so
far. Secondly, I am thinking to move the quality field on the S line to an
optional tag. Not many assemblers produce quality or per-base read depth.
Thirdly, more people prefer to explictly encode bubbles as multiple segments,
rather than inline them in the sequence. I will use explicit bubbles at least
in the initial iteration.

Here is the graph from the previous post in the updated format:

[Here](https://gist.github.com/cschin/133df440b9b10448a54f) is a comment from
Jason Chin -

> Some thought about Heng Li's proposal for assembly graph format
http://lh3.github.io/2014/07/19/a-proposal-of-the-grapical-fragment-assembly-
format/

some quick comments.

Is this format trying represent the raw overlaps or finally assembly graph or
both?

It seems to me that it is more suitable for the first. In the work to
represent diploid genome assembly, I had to do multiple level of reduction of
the graph from the initial string/overlap graph to simply the problem. if we
are looking at a more reduced assembly, we might have to deal with edges
corresponding to unitigs with the same in and out nodes. In this format, such
bubble paths (difference between them bigger than small indel) will be in
different row, the behavior of such edges with the same in and out node should
be defined. What I did for diploid work is to assign uid for each edges.

Also, I do think the final assembly should avoid the bidirectional edges. It
should be resolved by the assembler. From pragmatic point, it will confuse a
lot of biologists.

A number of additional comments and suggestions can be seen in Heng Li's
thread. Please feel free to add.

