---
title: 'PacBio: Debunking the Error Myth'
tags: []
categories:
- blog
---
Richard J Roberts, Mauricio O Carneiro and Michael C Schatz published a short
commentary in Genome Biology that is worth taking a look at.
<!--more-->

[Link](http://genomebiology.com/2013/14/6/405)

> The power of SMRT sequencing data lies both in its long read lengths and in
the random nature of the error process (Figure 2). It is true that individual
reads contain a higher number of errors: approximately 11% to 14% or Q12 to
Q15, compared with Q30 to Q35 from Illumina and other technologies. However,
given sufficient depth (8x or more, say), SMRT sequencing provides a highly
accurate statistically averaged consensus perspective of the genome, as it is
highly unlikely that the same error will be randomly observed multiple times.
Notoriously, other platforms have been found to suffer from systematic errors
that need to be resolved by complementary methods before the final sequence is
produced [16].

In a nutshell, smart (SMRT) people make mistakes and many smart persons are
whimsical :)

In our understanding, more than the errors, the type of error made the PacBios
so difficult for bioinformaticians. Bioinformatics tools and algorithms are
designed to cope with SNPs, whereas PacBio data have mostly indels. That is
why we took time to explain the point in the [(still incomplete and error-
prone) Pacbio tutorials](http://homolog.us/Tutorials/index.php?p=1.1&s=5).

