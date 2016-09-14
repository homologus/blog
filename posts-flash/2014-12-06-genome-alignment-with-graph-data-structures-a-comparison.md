---
title: 'Genome alignment with graph data structures: a comparison'
tags: []
categories:
- blog
---
[Interesting mathematical paper](http://www.biomedcentral.com/1471-2105/15/99)
<!--more-->

> Background

Recent advances in rapid, low-cost sequencing have opened up the opportunity
to study complete genome sequences. The computational approach of multiple
genome alignment allows investigation of evolutionarily related genomes in an
integrated fashion, providing a basis for downstream analyses such as
rearrangement studies and phylogenetic inference.

Graphs have proven to be a powerful tool for coping with the complexity of
genome-scale sequence alignments. The potential of graphs to intuitively
represent all aspects of genome alignments led to the development of graph-
based approaches for genome alignment. These approaches construct a graph from
a set of local alignments, and derive a genome alignment through
identification and removal of graph substructures that indicate errors in the
alignment.

Results

We compare the structures of commonly used graphs in terms of their abilities
to represent alignment information. We describe how the graphs can be
transformed into each other, and identify and classify graph substructures
common to one or more graphs. Based on previous approaches, we compile a list
of modifications that remove these substructures.

Conclusion

We show that crucial pieces of alignment information, associated with
inversions and duplications, are not visible in the structure of all graphs.
If we neglect vertex or edge labels, the graphs differ in their information
content. Still, many ideas are shared among all graph-based approaches. Based
on these findings, we outline a conceptual framework for graph-based genome
alignment that can assist in the development of future genome alignment tools.

