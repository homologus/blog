---
title: New Bioinformatics Blog to Keep an Eye on - James Knight
tags: []
categories:
- blog
---
![james-knight](http://www.homolog.us/blogs/wp-content/uploads/2014/08/james-
knight.jpg)
<!--more-->

[James Knight](http://www.linkedin.com/pub/james-knight/26/2b8/945)
(@knightjimr) joined Yale as a research scientist and director of
bioinformatics, and also started a blog, [where you can find a lot of useful
information](http://knightlab.commons.yale.edu/blog/). For those, who do not
know him, he developed the Newbler assembler for 454 reads and also
collaborated with Eugene Myers in the 90s, before Myers became world famous
(or rather made Craig Venter world famous).

[Graphs, Alignments, Variants and Annotations, pt.
1](http://knightlab.commons.yale.edu/gava-pt-1/)

> Note: This post, and following posts, were triggered by the recent post by
Heng Li, describing his proposed GFA format for assembly graph data. After a
twitter request for comments, my first tweet was that this was the right
person to do the format. My second tweet, after reading the post, was that the
format was a miss Heng rightly asked me to explain, and this begins that
explanation.

In recent years, there has been a growing trend toward developing a standard
file format for assemblies, specifically a graph-based format (since all of
the assemblers internal data structures hold a graph of one sort or another).
A number of years ago, it was the AMOS project that made the attempt, two to
three years ago, it was FASTG, and now this GFA format proposal.

When the FASTG format was really being talked about at the several conferences
two years ago, where by luck or by happenstance most of the lead authors of
the major NGS assemblers were present, I came really close to commenting on
the format, but refrained. The main reason is that I didnt see anything wrong
with the format itselfit does a very good job capturing the structure that
nearly all of the assemblers build, and is a usable format for organizing the
assemblies data. The thoughts in my mind were all about who was doing the
design, and, in a related way, why the FASTA format that we all know and love
(or dont love) is called the FASTA format.

[Graphs, Alignments, Variants and Annotations, pt. 2](Graphs, Alignments,
Variants and Annotations, pt. 2)

> Instead of heading towards the more theoretic graph design, the day after
writing part 1 of what is turning out to be a series, I focused on concrete
software changes that might answer the first question I posed in the previous
post (If you recast the problem as that of calling annotated variants, can you
speed up the current pipelines?), and that is what this post will be about.
The more theoretic graph design will be coming, but Im still thinking through
Heng Lis update describing previous work on graph algorithms, as well as a
recent slide deck he presented (the picture of where he is coming from is
becoming clearer).

