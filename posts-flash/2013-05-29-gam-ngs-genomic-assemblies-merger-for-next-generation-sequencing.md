---
title: GAM-NGS and REAPR Papers are Published
tags: []
categories:
- blog
---
Post-processing of genome assemblies is a big challenge. If you have five
assembly programs and run them on the same data set, you get five NGS
assemblies and in fact 50 considering the fact that you may choose to run the
program at multiple k-mer sizes. Several good papers came out to address the
'what next' question.
<!--more-->

[REAPR: a universal tool for genome assembly
evaluation](http://genomebiology.com/2013/14/5/R47/abstract)

> Methods to reliably assess the accuracy of genome sequence data are lacking.
Currently completeness is only described qualitatively and mis-assemblies are
overlooked. Here we present REAPR, a tool that precisely identifies errors in
genome assemblies without the need for a reference sequence. We have validated
REAPR on complete genomes or de novo assemblies from bacteria, malaria and
Caenorhabditis elegans, and demonstrate that 86% and 82% of the human and
mouse reference genomes are error-free, respectively. When applied to an
ongoing genome project, REAPR provides corrected assembly statistics allowing
the quantitative comparison of multiple assemblies. REAPR is available at
http://www.sanger.ac.uk/resources/software/reapr.

[GAM-NGS: genomic assemblies merger for next generation
sequencing](http://www.biomedcentral.com/1471-2105/14/S7/S6)

> Background

In recent years more than 20 assemblers have been proposed to tackle the hard
task of assembling NGS data. A common heuristic when assembling a genome is to
use several assemblers and then select the best assembly according to some
criteria. However, recent results clearly show that some assemblers lead to
better statistics than others on specific regions but are outperformed on
other regions or on different evaluation measures. To limit these problems we
developed GAM-NGS (Genomic Assemblies Merger for Next Generation Sequencing),
whose primary goal is to merge two or more assemblies in order to enhance
contiguity and correctness of both. GAM-NGS does not rely on global alignment:
regions of the two assemblies representing the same genomic locus (called
blocks) are identified through reads' alignments and stored in a weighted
graph. The merging phase is carried out with the help of this weighted graph
that allows an optimal resolution of local problematic regions.

Results

GAM-NGS has been tested on six different datasets and compared to other
assembly reconciliation tools. The availability of a reference sequence for
three of them allowed us to show how GAM-NGS is a tool able to output an
improved reliable set of sequences. GAM-NGS is also a very efficient tool able
to merge assemblies using substantially less computational resources than
comparable tools. In order to achieve such goals, GAM-NGS avoids global
alignment between contigs, making its strategy unique among other assembly
reconciliation tools.

Conclusions

The difficulty to obtain correct and reliable assemblies using a single
assembler is forcing the introduction of new algorithms able to enhance de
novo assemblies. GAM-NGS is a tool able to merge two or more assemblies in
order to improve contiguity and correctness. It can be used on all NGS-based
assembly projects and it shows its full potential with multi-library Illumina-
based projects. With more than 20 available assemblers it is hard to select
the best tool. In this context we propose a tool that improves assemblies
(and, as a by-product, perhaps even assemblers) by merging them and selecting
the generating that is most likely to be correct.

