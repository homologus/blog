---
title: De Bruijn graphs - I
tags:
- de-bruijn
- transcriptome assembly
- genome assembly
categories:
- blog
---
New algorithms for short read assembly ([categories B and
D](http://www.homolog.us/blogs/?p=109)) often use de Bruijn graphs to store
and represent sequence data. What is a de Bruijn graph and why is it so
popular for analyzing short read sequences? We will explain the concept here.
<!--more-->

De Bruijn graph is an efficient way to represent a sequence in terms of its
k-mer components. Although de Bruijn graphs can be used for [a broad range of
problems](http://en.wikipedia.org/wiki/De_Bruijn_graph), our discussion will
be limited to nucleotide sequences. Most papers talk about constructing de
Bruijn graphs from short reads and derive the genome sequence from the de
Bruijn graph. For simplicity, here we will first introduce de Bruijn graph of
a genome, and then explain how short reads fit into the picture.

A de Bruijn graph can be constructed for any sequence, short or long. Here is
a simple example -

![](http://www.homolog.us/blogs/wp-content/uploads/2011/07/i6-300x160.png)

In the above example, the sequence ATGGAAGTCGCGGAATC is split into overlapping
K-mers (K=7), and a directed graph is constructed with those 7-mers as nodes.
Edges are drawn between 7-mers adjacent on the original sequence. This method
of construction also ensures that connected nodes have overlaps of 6 (=K-1)
nucleotides.

The above example is simple, because none of the 7-mers repeated within the
original sequence. In the next example, we introduce some repetition. The
5'-most 7-mer in this example is identical to the 3'-most 7-mer (both marked
in blue). The de Bruijn graph forms a loop in this case.

![](http://www.homolog.us/blogs/wp-content/uploads/2011/07/i31-300x160.png)

Although the nodes displayed in the above examples did not show sequences for
both strands, in reality, each node is double-stranded as shown below -

![](http://www.homolog.us/blogs/wp-content/uploads/2011/07/i4-300x173.png)

In the above example, 3'-most 7-mer is the reverse complement of the 5'-most
7-mer. The links in the double-stranded de Bruijn graph were constructed
accordingly.

The steps shown above can be repeated to construct de Bruijn graph of a large
genome of any size. We note that even if a genome has 2 separate chromosomes,
the de Bruijn graphs may not remain separate, if those chromosomes have
overlapping K-mers as shown below.

![](http://www.homolog.us/blogs/wp-content/uploads/2011/07/i5-300x153.png)

All of the above examples considered K=7, but K can be any small or big
integer. At its lowest extreme, K can be 1. However, a K=1 de Bruijn graph is
not very useful as you can see from the following figure.

![](http://www.homolog.us/blogs/wp-content/uploads/2011/07/i21-300x260.png)

The above discussion introduces de Bruijn graphs for our purpose. Why they are
so popular for genome assembly programs will be explained in the following
post. Before closing, we will note few more points about de Bruijn graphs that
will be helpful in our future discussions.

1\. Given any sequence and K-mer size, we can create a de Bruijn graph in an
unique manner.

2\. The other direction is not true. Any de Bruijn graph cannot be resolved
into an unique sequence. Unless the de Bruijn graph is in its simplest form,
it usually resolves into many possible sequences.

3\. Larger the K-mers, more easy it is to convert the de Bruijn graph into an
unique sequence.

4\. Higher K-mer size generally requires more computer memory to store and
process the graph. Therefore, how much RAM a machine has sets the upper limit
for value of K.

Additional posts on the same topic -

[De Bruijn graphs - II](http://www.homolog.us/blogs/2011/07/29/de-bruijn-
graphs-ii//)

[De Bruijn Graphs - III](http://www.homolog.us/blogs/2011/07/31/de-bruijn-
graphs-iii/)

[How do sequencing errors affect de Bruijn
graphs?](http://www.homolog.us/blogs/2011/08/01/how-do-sequencing-errors-
affect-de-bruijn-graphs/)

[De Bruijn Graphs for Alternative Splicing and Repetitive
Regions](http://www.homolog.us/blogs/2011/08/09/de-bruijn-graphs-for-
alternative-splicing-and-repetitive-regions/)

[A Drawback of de Bruijn Graph
Approach](http://www.homolog.us/blogs/2011/08/11/a-drawback-of-de-bruijn-
graph-approach/)

[Using Mate Pair Information in de Bruijn
Graphs](http://www.homolog.us/blogs/2011/08/17/using-mate-pair-information-in-
de-bruijn-graphs/)

[Do de Bruijn Assemblers Work in Color
Space?](http://www.homolog.us/blogs/2011/09/09/do-de-bruijn-assemblers-work-
in-color-space/)

