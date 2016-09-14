---
title: Getting the Most Out of RNA-seq Data Analysis
categories:
- rnaseq
---
Another preprint on improving the quality of transcriptome assemblies, [this
time in peerJ](https://peerj.com/preprints/1198/).
<!--more-->

> A common research goal in transcriptome projects is to find genes that are
differentially expressed in different phenotype classes. Biologists might wish
to validate such gene candidates experimentally or use them for downstream
systems biology analysis. Producing a coherent differential expression
analysis from RNA-seq count data requires an understanding of how numerous
sources of variation such as the replicate size, the hypothesized biological
effect, and the specific method for making differential expression calls
interact. We believe an explicit demonstration of such interactions in real
RNA-seq data sets is of practical interest to the biologist. Results: Using
two large public RNA-seq data sets - one representing strong, and another
mild, biological response, we simulated different replicate size scenarios and
tested the performance of several commonly-used methods for calling
differentially expressed genes in each of them. Our results suggest that if
the biological response of interest in the different phenotype classes is
expected to be mild, then RNA-seq experiments should focus on validation of
differentially expressed gene candidates. At least triplicates must be used,
and the differentially expressed genes should be called using methods with
high positive predictive value such as NOISeq or GFOLD. In contrast, for
strong biological response, differentially expressed genes mined from
unreplicated experiments using NOISeq, ASC and GFOLD had between 30 to 50%
mean positive predictive value, an increase of more than 30-fold compared to
the case of mild biological response. Among methods with good positive
predictive value performance, having triplicates or more substantially
improved mean positive predictive value to over 90% for GFOLD, 60% for DESeq2,
50% for NOISeq, and 30% for edgeR. We found DESeq2 to be the most reasonable
method to call differentially expressed genes for systems level analysis as it
showed the best PPV and sensitivity trade-off (mean PPV and mean sensitivity ?
65% at replicate size of six). Conclusion: When biological effect size is
strong, NOISeq and GFOLD are effective tools for detecting differentially
expressed genes in unreplicated RNA-seq experiments for validation work.
Having triplicates or more enables DESeq2 to detect sufficiently large numbers
of reliable gene candidates for downstream systems level analysis. When
biological effect size is weak, systems level investigation is not possible,
and no meaningful result can be obtained in unreplicated experiments.
Nonetheless, NOISeq or GFOLD may yield limited numbers of candidates with good
validation potential when triplicates or more are available.

