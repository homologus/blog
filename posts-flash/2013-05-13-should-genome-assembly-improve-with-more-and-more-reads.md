---
title: Should Genome Assembly Improve with More and More Reads?
tags: []
categories:
- blog
---
Conventional wisdom says yes, but that may not work for de Bruijn graph-based
assemblers. Last year, we were experimenting with Velvet and noticed something
strange. When we randomly removed half of the reads from a genomic library,
the 'assembly quality' seemed to have improved. Assembly quality was measured
in terms of N50 of scaffolds and not using any other detailed analysis. What
was going on?
<!--more-->

We did k-mer analysis of the assembled scaffolds. It was clear that the
assembly was wrong, because some k-mers supposedly present only once in the
genome were found more than 5-6 times in the assembly. Here was our best
explanation for the observation. A de Bruijn graph-based assembler [splits all
reads into k-mers and forms a giant
graph](http://homolog.us/Tutorials/index.php?p=3.2&s=1). That graph is
resolved into contigs. At times, the program sees overlaps between two
branches (such as the [second figure
here](http://homolog.us/Tutorials/index.php?p=3.4&s=1)) and creates multiple
contigs all terminating at the junction in the figure.

What happens, when you remove some reads? The data becomes sparse and one or
other branch of the graph may not appear due to sparseness. The assembler does
not pause at the junction and evaluates one or other branch as a contiguous
sequence, even when it is not.

The second best explanation was a possible defect in Velvet's scaffolding
routine. We did not have to explore further to resolve between the
possibilities.

