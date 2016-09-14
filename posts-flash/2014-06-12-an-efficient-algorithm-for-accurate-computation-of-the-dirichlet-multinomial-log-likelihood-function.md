---
title: An efficient algorithm for accurate computation of the Dirichlet-multinomial
  log-likelihood function
tags: []
categories:
- blog
---
Readers working on metagenomics may find [this new Bioinformatics paper](http:
//bioinformatics.oxfordjournals.org/content/30/11/1547.abstract.html?etoc)
useful (h/t: @infoecho)
<!--more-->

> The Dirichlet-multinomial (DMN) distribution is a fundamental model for
multicategory count data with overdispersion. This distribution has many uses
in bioinformatics including applications to metagenomics data,
transctriptomics and alternative splicing. The DMN distribution reduces to the
multinomial distribution when the overdispersion parameter ? is 0.
Unfortunately, numerical computation of the DMN log-likelihood function by
conventional methods results in instability in the neighborhood of Graphic. An
alternative formulation circumvents this instability, but it leads to long
runtimes that make it impractical for large count data common in
bioinformatics. We have developed a new method for computation of the DMN log-
likelihood to solve the instability problem without incurring long runtimes.
The new approach is composed of a novel formula and an algorithm to extend its
applicability. Our numerical experiments show that this new method both
improves the accuracy of log-likelihood evaluation and the runtime by several
orders of magnitude, especially in high-count data situations that are common
in deep sequencing data. Using real metagenomic data, our method achieves
manyfold runtime improvement. Our method increases the feasibility of using
the DMN distribution to model many high-throughput problems in bioinformatics.
We have included in our work an R package giving access to this method and a
vingette applying this approach to metagenomic data.

