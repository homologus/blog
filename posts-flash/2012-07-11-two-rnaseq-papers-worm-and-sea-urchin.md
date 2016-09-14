---
title: Two RNAseq Papers - Worm and Sea urchin
tags: []
categories:
- rnaseq
---
Two RNAseq papers ([sea urchin S. purpuratus](http://genome.cshlp.org/content/
early/2012/06/18/gr.139170.112.abstract) and [worm C. brrigsae](http://genome.
cshlp.org/content/early/2012/07/05/gr.134601.111.abstract?cited-
by=yes&legid=genome;gr.134601.111v1)) came out in the advanced online section
of Genome Research. They prove something that we were aware of for long time.
It is that a large fraction of computationally derived gene models published
as part of large-scale genome assembly projects were incorrect. How did we
know? We did tiling array experiments on various genomes and saw major
discrepancies between models and empirically observed gene structures ([sea
urchin](http://stke.sciencemag.org/cgi/content/full/sci;314/5801/960) and
[human](http://www.sciencemag.org/content/306/5705/2242.long)). You can view
the sea urchin tiling data [here](http://www.systemix.org/Codes101/viewer-old
/plot-header.php?org=SU3&expt=NASA%3Asignal&tr=GLEAN&scaffold=4&strand=C&begin
=1&end=50000&Submit1=Array+data) and compare with the predicted genes (green)
to see the discrepancies.
<!--more-->

RNAseq is more accurate than tiling array approach, because it gives the
underlying sequences of genes, whereas with tiling arrays, the biologists are
limited by whichever probes are placed on the arrays. So, it is reassuring
that the RNAseq approach found major inaccuracies in the existing gene models.
From the abstract of sea urchin paper -

> The genome had initially been annotated by use of computational gene model
prediction algorithms. A large fraction of these predicted genes were
recovered in the transcriptome when the reads were mapped to the genome and
appropriately filtered and analyzed. However, in a manually curated subset, we
discovered that over half the computational gene model predictions were
imperfect, containing errors such as missing exons, prediction of
non-?existent exons, erroneous intron/exon boundaries, fusion of adjacent
genes, and prediction of multiple genes from single genes.

Two things puzzle us about the above report, however.

i) Our tiling array experiment showed expressions in many other areas of the
genome, where no genes were predicted by computational model. Did the RNAseq
experiment confirm or reject those observed expressions? Given that no mention
of the previous tiling-array experiment was done in the paper or references,
we suspect the authors did not try.

ii) Scientists working on most other eukaryotic organisms are discovering
long-noncoding RNAs. Did the above study see any such gene? The discussion
seem to be limited to the genes already predicted by computational methods.

The [C. briggsae
paper](http://genome.cshlp.org/content/early/2012/07/05/gr.134601.111.abstract
?cited-by=yes&legid=genome;gr.134601.111v1) dealt with quite different problem
than sea urchin. Its cousin organism (_C. elegans_) has been extensively
annotated by all possible methods including RNAseq. Then those gene models
were computationally inferred on _C. briggsae_, which is only a closely
related worm. So, RNAseq in C. briggsae was done to perfect the gene models.

> In this study, we have used RNA-seq reads to annotate transsplicing sites,
splicing leaders, and operons in C. briggsae. We annotated trans-splicing
sites and trans-splicing leaders (SLs) through examining misalignments between
SL-containing transcript sequences and the C. briggsae genome sequences.

Those working on de novo assembly of transcriptomes will not find much in the
above papers. Although the sea urchin paper used Trinity for one set, most of
the analysis in both papers are done using standard mapping tools to map reads
on reference genomes.

