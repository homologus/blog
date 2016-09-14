---
title: Estimates of Positive Darwinian Selection Are Inﬂated by Errors in Sequencing,
  Annotation and Alignment
tags: []
categories:
- blog
---
These days it is very easy to sequence the genome of an unknown organism from
short reads, but all subsequent steps - assembly, gene prediction, annotation
etc. add quite a bit of noise. Therefore, when someone makes a biological
observation from such noisy data, it is important to properly discount it for
such uncertainties.
<!--more-->

We have been going through a PAML analysis of accelerated evolution and were
wondering about how the short read noise would affect the observation of large
amount of accelerated evolution. We thoroughly checked all software pipelines
to make sure there was no procedural error. However, that did not rule out
noise from steps assumed to be accurate by the PAML approach.

To gain full understanding of the mathematics behind the calculation, we went
to ["Phylogenetic Analysis by Maximum Likelihood
(PAML)"](http://abacus.gene.ucl.ac.uk/software/paml.html) website by Ziheng
Yang, and also read the 1998 paper ["Likelihood Ratio Tests for Detecting
Positive Selection and Application to Primate Lysozyme
Evolution"](http://mbe.oxfordjournals.org/content/15/5/568.full.pdf) by the
same author.

Further backtracking on relevant papers got us to other important contributors
in the field. One key contributor had been Masatoshi Nei, whose recent book on
mutation-driven evolution was covered in our commentary - [Darwin Never Proved
Natural Selection is the Driving Force of Evolution Because It
Isnt](http://www.homolog.us/blogs/ncrna/2014/03/05/mutationism/). Other major
early researchers were W. H. Li and T. Gojobori. Especially, the following
1986 paper - ["Simple methods for estimating the numbers of synonymous and
nonsynonymous nucleotide
substitutions"](http://www.ncbi.nlm.nih.gov/pubmed/3444411) by Nei and
Gojobori - became the basis for many subsequent numerical programs for
computing accelerated evolution. Nei and Walter Fitch, who wrote the [1967
Science paper on constructing first phylogenetic tree](http://biologie-lernpro
gramme.de/daten/programme/js/homologer/daten/lit/fitch_phylogeny_construction.
pdf), also started the respected journal [Molecular Biology and
Evolution](http://mbe.oxfordjournals.org/).

[The wiki page of Nei](http://en.wikipedia.org/wiki/Masatoshi_Nei) led us to
[one of his early graduate students](http://en.wikipedia.org/wiki/Dan_Graur),
who kindly pointed us to his own paper describing exactly what we were worried
about. The claims of positive selection are often vastly inflated by errors in
sequencing, annotation and alignment as [he showed in his 2009
paper](http://nsmn1.uh.edu/dgraur/ArticlesPDFs/schneider-et-al-2009.pdf). Some
of his findings are really alarming (check macaque for example) and even more
so, given that his paper covered the era of Sanger sequencing, when genomes
were supposedly 'better'.

>

Published estimates of the proportion of positively selected genes (PSGs) in
human vary over three orders of magnitude. In mammals, estimates of the
proportion of PSGs cover an even wider range of values. We used 2,980
orthologous protein-coding genes from human, chimpanzee, macaque, dog, cow,
rat, and mouse as well as an established phylogenetic topology to infer the
fraction of PSGs in all seven terminal branches. The inferred fraction of PSGs
ranged from 0.9% in human through 17.5% in macaque to 23.3% in dog. We found
three factors that in?uence the fraction of genes that exhibit telltale signs
of positive selection: the quality of the sequence, the degree of
misannotation, and ambiguities in the multiple sequence alignment. The
inferred fraction of PSGs in sequences that are de?cient in all three criteria
of coverage, annotation, and alignment is 7.2 times higher than that in genes
with high trace sequencing coverage, known annotation status, and perfect
alignment scores. We conclude that some estimates on the prevalence of
positive Darwinian selection in the literature may be in?ated and should be
treated with caution.

Maybe it is time to have a 'positive selection-a-thon' to find out where
things are after NGS. For those, who are worried like us about making bad
claims about accelerated evolution in papers, Dan Graur suggested to check for
the following things -

>

1\. If the sequences that have the lowest sequencing coverage turn out to be
the fastest evolving you will know that there is a bias.

2\. If the least reliable parts of the alignment tend to evolve the fastest,
ditto.

3\. Since error tend not to distinguish between synonymous and nonsynonymous
substitution, one may find in protein coding genes weird ratios of Ka/Ks in
low quality segments, or badly aligned ones.

