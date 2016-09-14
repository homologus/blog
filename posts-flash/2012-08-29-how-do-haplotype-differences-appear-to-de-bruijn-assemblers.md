---
title: How Do Haplotype Differences Appear to de Bruijn Assemblers ?
tags:
- Polymorphic
- Phasing
categories:
- blog
---
In the context of [previous commentary on Compass
graphs](http://www.homolog.us/blogs/2012/08/28/hapcompass-an-elegant-use-of-
graphs-for-haplotype-assemblyphasing/), we were thinking about how the de
Bruijn graphs would treat haplotype differences.
<!--more-->

The best way to visualize de Bruijn graph structure is to start from the
genome and draw the graph [based on
k-mers](http://www.homolog.us/blogs/2011/07/28/de-bruijn-graphs-i/). The only
difference with previous examples is that to account for haplotype difference,
you need to draw two near-identical copies of the chromosome side-by-side and
create a combined graph. In regions, where two chromosomes are identical,
graph structures will merge. Where the chromosomes are different, you will see
two branches of the graph as shown below. Circles in the graph represent k-mer
nodes, arrows represent their connections, and dark shaded lines show read
distribution. For simplicity, we have shown unidirectional arrows, but de
Bruijn graphs of genomes are bidirectional accounting for two strands.

![](http://www.homolog.us/blogs/wp-content/uploads/2012/08/fig2-300x115.png)

Interestingly, the graph structure for SNP shown above is not different from
[sequencing errors](http://www.homolog.us/blogs/2011/08/01/how-do-sequencing-
errors-affect-de-bruijn-graphs/) (shown below). The difference is in read
distribution. In case of sequencing error, erroneous branch is less well-
traveled by one or two reads, whereas SNP difference between two chromosomes
will show near equal distribution of reads among the branches of the de Bruijn
graph.

![](http://www.homolog.us/blogs/wp-content/uploads/2012/08/fig1-300x66.png)

How about insertion-deletions? We borrowed an old figure on [alternatively
spliced genes](http://www.homolog.us/blogs/2011/08/09/de-bruijn-graphs-for-
alternative-splicing-and-repetitive-regions/), because graph structures for
indels and alt-splices are similar.

![](http://www.homolog.us/blogs/wp-content/uploads/2012/08/fig3-300x184.png)

