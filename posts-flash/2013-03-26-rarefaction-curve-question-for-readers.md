---
title: Rarefaction Curve - Question for Readers
tags: []
categories:
- rnaseq
---
I received the following question from a reader few days back and planned to
go through the linked paper to answer back. However, other work related to
submission and setting up of tutorial kept me occupied. It just occurred to me
that many of our readers are far more experienced than me to readily answer
his question.
<!--more-->

>

I would like to know if you come across of *Rarefaction curve* in some of the
published papers these days. One of it i came across is present in a paper
called "*RNA-sequence analysis of human B-cells"([image](http://www.ncbi.nlm.n
ih.gov/pmc/articles/PMC3106332/figure/F4/))

Could i please know, if you have any idea on how to plot these kind of figures
and find if the depth of the sequencing is really sufficient or not. Because,
the only way i can think of is doing multiple assemblies by taking different
subset of reads with different number of reads which might not be robust, or
is there any other method to gain information if depth of sequencing.

Would someone please give a shot?

\------------------------

Edit.

Reader Istvan Albert's comment provides us with a very good answer and I am
copying it here for more visibility. Sometimes search engines give more weight
to the main text than the comment section.

> The purpose of a rarefaction curve is to demonstrate that the sampling is
sufficiently high to fully represent (saturate) the quantity of interest.
Otherwise we would not be able to reliably compare quantities derived from
different measurements. Curves that saturate indicate that collecting more
data would not lead to discovering say more transcripts etc.

To create such a curve select a subsample of your original data and compute
the quantity of interest, then increase the size of the subsample and repeat
the experiment. The x axis is the size of the sample, the y is the measurement
of interest. This will be a so called collector curve. Now overlaying many
collector curves (in essence repeating the subsampling for every sample size)
would be a rarefaction curve.

ScottC posted [this helpful wiki
link](http://en.wikipedia.org/wiki/Rarefaction_\(ecology\)).

> In ecology, rarefaction is a technique to assess species richness from the
results of sampling. Rarefaction allows the calculation of species richness
for a given number of individual samples, based on the construction of so-
called rarefaction curves. This curve is a plot of the number of species as a
function of the number of samples. On the left, the steep slope indicates that
a large fraction of the species diversity remains to be discovered. If the
curve becomes flatter to the right, a reasonable number of individual samples
have been taken: more intensive sampling is likely to yield only few
additional species.

The issue that occurs when sampling various species in a community is that the
larger the number of individuals sampled, the more species that will be found.
Sampling curves generally rise very quickly at first and then level off
towards an asymptote as fewer new species are found per unit of individuals
collected. Rarefaction curves are created by randomly re-sampling the pool of
N samples multiple times and then plotting the average number of species found
in each sample (1,2, ... N). "Thus rarefaction generates the expected number
of species in a small collection of n individuals (or n samples) drawn at
random from the large pool of N samples." [1] Rarefaction curves generally
grow rapidly at first, as the most common species are found, but the curves
plateau as only the rarest species remain to be sampled.

