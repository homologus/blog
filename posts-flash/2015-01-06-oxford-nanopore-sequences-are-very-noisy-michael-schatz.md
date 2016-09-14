---
title: Oxford Nanopore Sequences are Very Noisy - Michael Schatz
tags: []
categories:
- blog
---
![mschatz](http://www.homolog.us/blogs/wp-content/uploads/2015/01/mschatz-
197x300.jpg)
<!--more-->

A few months back, when I asked Michael Schatz about the error rate of Oxford
Nanopore, he gave me a very cryptic answer ('assembly is possible, as long as
there is more signal than noise' - paraphrased). Thankfully, [his newly posted
biorxiv paper](http://biorxiv.org/content/early/2015/01/06/013490) addresses
the issue properly.

Major points -

1\.

> Of the 267,768 reads produced by our 30 sequencing runs, 64,849 reads (24%)
aligned to the reference yeast genome, and 31,013 (11%) aligned to the known
spike-in sequence used for calibrating the instruments. The remaining 65% of
reads did not show significant similarity to the W303 genome or spike-in
sequence, presumably because of insufficient read quality (Supplemental note
4).

[**Note: The comparative numbers for Pacbio are over 95%. This is very
important for de novo assembly from long reads alone, because one does not
know which reads are real and which are not.**]

2\.

> Supplemental Figure S5A shows that the mean identity to the reference of 1D
reads was 64% while 2D reads produced many reads exceeding 75% identity.

[**Note: The comparative number for Pacbio is 85% identity. This is important
for de novo assembly from long reads alone, because when one aligns long noisy
reads with 85% accuracy against long noisy reads with 85% accuracy, the
relative similarity becomes 70% (Edited, thanks Cedric). For 75% accuracy of
reads, the relative difference will be 50% !! **]

3\.

> Of the reads that align, the overall coverage distribution approximated a
Poisson distribution centered at 35x coverage, although some over-dispersion
was observed that was better modeled by a Negative Binomial distribution
(Supplemental Figure S5C). To examine some of the sources of the over-
dispersion we also examined the coverage as a function of the GC composition
of the genome. Between 20% and 60% GC content, the coverage was fairly
uniform, while at high and low GC content the coverage is more variable
partially explaining some of the regions of the genome lacking raw read
coverage (Supplemental Figure S5D).

[**Note: Pacbio reads do not show GC bias. This is important for assembling
Plasmodium and other genomes, which are very AT-rich. Also, it is important
for assembling the AT-rich parts of the genome.**]

4\.

> The very longest reads tend not to be alignable at all, suggesting that the
longest reads may be extremely low quality or include other artifacts of the
sequencing process.

[**Note: Very longest Pacbio reads are not trustworthy either.**]

\---------------------------------------

The remaining paper is not very useful. I have two major objections -

(i) You have to look very hard to find out that they are doing hybrid assembly
and not a straight nanopore-only assembly. Why is it so difficult to mention
that simple fact in the title/abstract?

(ii) If they are doing long-short assembly of yeast genome anyway, why stops
them from doing a comparison with Pacbio-Illumina hybrid assembly and mention
the comparative results in the abstract?

