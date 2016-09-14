---
title: 'Arxiv Paper: Biological Averaging in RNA-Seq'
tags: []
categories:
- rnaseq
---
In 2008, Jay Shendure wrote - ["The beginning of the end for microarrays?"](ht
tp://www.nature.com/nmeth/journal/v5/n7/abs/nmeth0708-585.html). Now we are
possibly seeing 'end of the end' with microarray-related ideas being brought
into RNAseq analysis.
<!--more-->

[Link](http://arxiv.org/pdf/1309.0670v1.pdf)

> RNA-seq has become a de facto standard for measuring gene expression.
Traditionally, RNA-seq experiments are mathematically averaged they sequence
the mRNA of individuals from di?erent treatment

groups, hoping to correlate phenotype with di?erences in arithmetic read count
averages at shared loci of

interest. Alternatively, the tissue from the same (or more) individuals may be
pooled prior to sequencing

in what we refer to as a biologically averaged design. As mathematical
averaging sequences all individuals

it controls for both biological and technical variation; however, is the
statistical resolution gained always

worth the additional cost? To compare biological and mathematical averaging,
we examined theoretical

and empirical estimates of statistical e?ciency and relative cost e?ciency.
Though less e?cient at a ?xed

sample size, we found that biological averaging can be more cost e?cient than
mathematical averaging,

especially if biological variation is large and biologically averaged
individuals can be pooled evenly. With

this motivation, we developed a di?erential expression classi?er, ICRBC, that
can detect alternatively

expressed genes between biologically averaged samples. In simulation studies,
we found that biological

averaging and subsequent analysis with our classi?er performed comparably to
existing methods, such

as ASC, edgeR, and DESeq, especially when individuals were pooled evenly and
less than 20% of the

regulome was expected to be di?erentially regulated. In two technically
distinct mouse datasets and one

plant dataset, we found that our method was over 87% concordant with edgeR for
the 100 most signi?cant

features. While biological averaging cannot provide the same statistical
resolution as a well replicated

mathematically averaged experiment, it may su?ciently control biological
variation to a level that di?erences in gene expression may be detectable. In
such situations, ICRBC can enable reliable exploratory

analysis at a fraction of the cost, especially when interest lies in the most
di?erentially expressed loci.

