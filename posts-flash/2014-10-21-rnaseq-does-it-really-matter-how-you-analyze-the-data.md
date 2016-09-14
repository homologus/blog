---
title: 'RNAseq: Does it Really Matter How You Analyze the Data?'
categories:
- rnaseq
---
This is certainly an interesting paper that will make the statisticians
working on low-level processing of RNAseq data unhappy. Our experience has
been in agreement with their final statement -
<!--more-->

> Our results suggest that RNA-Seq analysis should be extremely biology-aware,
and special effort should be devoted to optimizing the last stage of the
analysis, i.e. search for the functional patterns that form a unique signature
of cellular response to the conditions of interest.

\----------------------------------------------------------------------

[Making sense of RNA-Seq data: from low-level processing to functional
analysis](http://biorxiv.org/content/early/2014/10/17/010488)

> Numerous methods of RNA-Seq data analysis have been developed, and there are
more under active development. In this paper, our focus is on evaluating the
impact of each processing stage; from pre-processing of sequencing reads to
alignment/counting to count normalization to differential expression testing
to downstream functional analysis, on the inferred functional pattern of
biological response. We assess the impact of 6,912 combinations of technical
and biological factors on the resulting signature of transcriptomic functional
response. Given the absence of the ground truth, we use two complementary
evaluation criteria: a) consistency of the functional patterns identified in
two similar comparisons, namely effects of a naturally-toxic medium and a
medium with artificially reconstituted toxicity, and b) consistency of results
in RNA-Seq and microarray versions of the same study. Our results show that
despite high variability at the low-level processing stage (read pre-
processing, alignment and counting) and the differential expression calling
stage, their impact on the inferred pattern of biological response was
surprisingly low; they were instead overshadowed by the choice of the
functional enrichment method. The latter have an impact comparable in
magnitude to the impact of biological factors per se.

