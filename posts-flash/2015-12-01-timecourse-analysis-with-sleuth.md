---
title: Timecourse analysis with Sleuth
categories:
- rnaseq
---
> An extremely interesting application of RNA-sequencing analysis is to study
samples over a time series. This allows you to identify patterns of expression
over some response to a stimuli or developmental progression.
<!--more-->

While Sleuth together with the Kallisto from the Pachter lab makes it easy to
perform differential expression analysis in the two-condition case of an RNA-
seq experiment, there is still some confusion about how to perform DE over a
time series. I thought it would be useful to write an example text of how to
detect DE transcripts over a time course with Sleuth.

The first problem is to define what we mean by differentially expressed in the
context of a time series. For a treatment-vs-control type experiment it is
simple: What genes are higher or lower expressed in the treatment condition
compared to the control? The first generalization which comes to mind would be
to find genes whose level increase or decrease with the time points. This
means finding correlation with time points and boils down to linear regression
of expression with time points. However, this will mask potentially
interesting genes which could for example peak in the middle of the time
series. What we want is to find if the expression of a gene follows a general
pattern to a higher degree than just noise.

[Continue reading](http://nxn.se/post/134227694720/timecourse-analysis-with-
sleuth)

