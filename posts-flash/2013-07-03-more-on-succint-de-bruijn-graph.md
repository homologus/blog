---
title: More on Succint de Bruijn Graph
tags: []
categories:
- blog
---
Several months back, we wrote on Alex Bowe's work on Succint de Bruijn graph,
and where it fits in the big picture of genome assemblers.
<!--more-->

[Succinct de Bruijn Graphs from Tetsuo Shibuyas
Group](http://www.homolog.us/blogs/blog/2012/10/08/succinct-de-bruijn-graphs-
from-tetsuo-shibuyas-group/)

**Alex Bowes Succinct de Bruijn Graphs**

> The succint de Bruijn graph structure proposed by Bowe et al. reduces memory
requirement significantly from the derived theoretical limit of
Conway/Bromage, while storing all the edges of de Bruijn graph. From their
paper:

"For example, the succinct representation of Conway and Bromage [5] uses
40.8GB for storing a de Bruijn graph with m =12,292,819,311 edges and k = 27
(28.5 bits per edge). On the other hand, if we use an efficient implementation
of rank/select data structures [17] for our representation, the estimated size
is less than 5 bits per edge. Therefore the above graph is stored in less than
8GB."

How do they do that? They figured out a way to perform Burrows Wheeler
transform on the nodes/edges of a de Bruijn graph and store the graph in
compressed manner, while being able to access the nodes rapidly. In their
paper, they presented an example of a de Bruijn graph of three reads in Fig. 1
and explained how it looked in compressed form in Fig. 2. They also provide
sample code for their compression algorithm here. The code comprises of only
one 500 line long C-program sdg.c that compiles very easily.

If you want to learn more about it, Alex has written a blog post himself.

[Succinct de Bruijn Graphs](http://alexbowe.com/succinct-debruijn-graphs/)

> This post will give a brief explanation of a Succinct implementation for
storing de Bruijn graphs, which is recent (and continuing) work I have been
doing with Sadakane.

Using our new structure, we have squeezed a graph for a human genome (which
took around 300 GB of memory if using previous representations) down into 2.5
GB. In addition, the construction method allows much of the work to be done on
disk. Your computer might not have 300 GB of RAM, but you might have 2.5 GB of
RAM and a hard disk.

Please read the rest in [Alex's blog](http://alexbowe.com/succinct-debruijn-
graphs/). This is really fascinating material, and Sadakane is a leader in
BWT/FM.

