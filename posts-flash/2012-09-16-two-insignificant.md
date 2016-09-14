---
title: Creating Confusion
tags: []
categories:
- blog
---
Thanks to Nikolay Vyahhi and Aaron Hardin for forwarding us papers related to
[SPAdes assembler and rectangular
graphs](http://www.homolog.us/blogs/2012/09/12/from-de-bruijn-graphs-to-
rectangle-graphs-for-genome-assembly/). Over the weekend, I have been busy
understanding the algorithms and [read in a related
paper](http://www.pnas.org/content/98/17/9748.long) that de Bruijn graph
approach assembles short reads by breaking the reads to even shorter pieces.
Isn't that fascinating?
<!--more-->

At that point, my little son came asking for help with his LEGO puzzles. He
got the set as a gift on his birthday. I wanted to show him new tricks, and so
I took a hammer to pulverize his LEGO pieces. Isn't that de Bruijn graph
method all about? Now I am left with two very complex papers and one very
unhappy kid. Does anyone have Pavel Pevzner's phone number?

Jokes apart, de Bruijn graphs do not really break the sequences apart into
tiny pieces, because the 'graph' structure keeps the pieces connected.
Remember a graph has vertices and edges. The pulverized LEGO pieces represent
the vertices, but in a de Bruijn graph, they are still conceptually joined at
the hip by the edges.

At that time, I also read [Minia paper by Rayan
Chikhi](http://minia.genouest.org/) and learned that de Bruijn graphs
(genomic) are different from most other graph structures studied in CS class,
because they can completely get rid of edges. If you have a data structure
that stores all nodes of a de Bruijn graph, you do not need to store the edges
in a separate structure. The edges can be recreated by starting from a node
and checking whether its eight potential neighbors exist or not.

I hope I confused you enough on a Monday morning. Further explanation will be
added after I get back from the toy store with a new box of LEGOs.

