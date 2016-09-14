---
title: Why Weight? Modelling Sample and Observational Level Variability Improves Power
  in RNA-seq Analyses
categories:
- rnaseq
---
[Link](http://nar.oxfordjournals.org/content/early/2015/04/28/nar.gkv412.full)
<!--more-->

> Variations in sample quality are frequently encountered in small RNA-
sequencing experiments, and pose a major challenge in a differential
expression analysis. Removal of high variation samples reduces noise, but at a
cost of reducing power, thus limiting our ability to detect biologically
meaningful changes. Similarly, retaining these samples in the analysis may not
reveal any statistically significant changes due to the higher noise level. A
compromise is to use all available data, but to down-weight the observations
from more variable samples. We describe a statistical approach that
facilitates this by modelling heterogeneity at both the sample and
observational levels as part of the differential expression analysis. At the
sample level this is achieved by fitting a log-linear variance model that
includes common sample-specific or group-specific parameters that are shared
between genes. The estimated sample variance factors are then converted to
weights and combined with observational level weights obtained from the
meanvariance relationship of the log-counts-per-million using voom. A
comprehensive analysis involving both simulations and experimental RNA-
sequencing data demonstrates that this strategy leads to a universally more
powerful analysis and fewer false discoveries when compared to conventional
approaches. This methodology has wide application and is implemented in the
open-source limma package.

