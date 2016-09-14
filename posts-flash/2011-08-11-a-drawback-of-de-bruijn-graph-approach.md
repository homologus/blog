---
title: A Drawback of de Bruijn Graph Approach
tags:
- de-bruijn
- genome assembly
categories:
- blog
---
In [our first commentary on de Bruijn
graphs](http://www.homolog.us/blogs/?p=123), we explained how de Bruijn graph
can be constructed for any genome.
<!--more-->

![](http://www.homolog.us/blogs/wp-content/uploads/2011/08/db1-300x133.png)

In the [second commentary](http://www.homolog.us/blogs/?p=158), we argued that
a de Bruijn graph created from millions of short reads is identical to the de
Bruijn graph of the underlying genome, if coverage is perfect. So, the
assembly problem reduces to figuring out the genome from its de Bruijn graph,
i.e. the inverse problem of graph creation.

At this point, you may be wondering why de Bruijn graphs were not widely used
in the prehistoric era of sequencing (Sanger sequencing era) given that they
are the greatest things invented since sliced bread. The answer is simple. De
Bruijn graphs do not preserve positional information.

Let me elaborate. In the commentary on [de Bruijn graphs for alternative
splicing and repetitive regions](http://www.homolog.us/blogs/?p=314), we
showed how different sequences can generate identical de Bruijn graph. Let us
say we create de Bruijn graph from a long Sanger read. If the Sanger read has
repetitive structure, de Bruijn graph for the read itself will contain loop.
That means we cannot go back from the de Bruijn graph to the read. However,
the read itself is a true representation of a part of the genome. By
converting it into de Bruijn graph, we lose what is already known about that
part of the genome.

Loss of positional information is the biggest drawback of going from sequence
space to de Bruijn graph space. Longer the read size, more one has to lose.

Additional posts on the same topic -

[De Bruijn graphs - I](http://www.homolog.us/blogs/2011/07/28/de-bruijn-
graphs-i/)

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

[Using Mate Pair Information in de Bruijn
Graphs](http://www.homolog.us/blogs/2011/08/17/using-mate-pair-information-in-
de-bruijn-graphs/)

[Do de Bruijn Assemblers Work in Color
Space?](http://www.homolog.us/blogs/2011/09/09/do-de-bruijn-assemblers-work-
in-color-space/)

