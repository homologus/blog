---
title: 'QUAST: Quality Assessment Tool for Genome Assemblies'
tags: []
categories:
- blog
---
Last year, we wrote extensively about the SPAdes paper
([here](http://www.homolog.us/blogs/2012/09/12/from-de-bruijn-graphs-to-
rectangle-graphs-for-genome-assembly/),
[here](http://www.homolog.us/blogs/2012/09/17/few-thoughts-on-spades-papers/),
[here](http://www.homolog.us/blogs/2012/09/12/from-de-bruijn-graphs-to-
rectangle-graphs-for-genome-assembly/),
[here](http://www.homolog.us/blogs/2012/10/07/more-on-rectangle-graphs/) and
[here](http://www.homolog.us/blogs/2012/10/10/multi-kmer-de-bruijn-graphs/)).
In additional to their innovative algorithm, the original SPAdes paper could
also be considered as a mini-Assemblathon, because they ran all existing
assembly programs on a small test set and designed their own assessment tools
to convince themselves and others that the tests were appropriate. [QUAST
paper linked here](http://bioinformatics.oxfordjournals.org/content/early/2013
/02/20/bioinformatics.btt086) presents those quality assessment tools in more
details.
<!--more-->

> **Summary:** Limitations of genome sequencing techniques have lead to dozens
of assembly algorithms, none of which is perfect. A number of methods for
comparing assemblers have been developed, but none is yet a recognized
benchmark. Further, most existing methods for comparing assemblies are only
applicable to new assemblies of finished genomes; the problem of evaluating
assemblies of previously unsequenced species has not been adequately
considered. Here we present QUAST a QUality ASsessment Tool to evaluate and
compare genome assemblies. This tool improves on leading assembly comparison
software with new ideas and quality metrics. QUAST can evaluate assemblies
both with a reference genome as well as without a reference. QUAST produces
many reports, summary tables, and plots, to help scientists in their research
and in their publications. In this study, we used QUAST to compare several
genome assemblers on three data sets. QUAST tables and plots for all of them
are available in the Supplementary Material and interactive versions of these
reports are on the QUAST website.

**Availability:** http://bioinf.spbau.ru/quast 

**Contact:** gurevich@bioinf.spbau.ru 

If you did not realize, the wonderful Rosalind educational platform comes from
the same group. They are also planning to start [bioinformatics training
course at Coursera](https://www.coursera.org/course/bioinformatics).

\-----------------------------------

Edit.

Nikolay Vyahhi, an author of QUAST, emailed us [another QUAST-related
document](https://docs.google.com/document/d/10k4vaMPAsFhmBky1Gn-
VlrnxbTHR3tGgD9sE1msMp3o/edit) that may help you get started.

**QUAST announcement**

> We'd like to present QUAST, a convenient tool for assembly evaluation. It
has already been mentioned on Homologus when it was employed for [SPAdes vs.
Ray benchmarking](http://www.homolog.us/blogs/2012/10/01/heads-up-for-readers-
spades-vs-ray-benchmarking-is-done/), and lately Rayan Chikhi recommended it
in his [guides](http://www.homolog.us/blogs/2013/01/10/two-helpful-guides-for-
those-working-on-genome-assembly/). The other day QUAST paper has been
accepted to Bioinformatics, and now it is available in [Advanced Access](http:
//bioinformatics.oxfordjournals.org/content/early/2013/02/20/bioinformatics.bt
t086).

QUAST computes a number of well-known metrics, including contig accuracy,
number of genes discovered, N50, and others. It also introduces some new
statistics, like NA50 (see paper). An analysis results in summary tables
available in various formats, including human-readable plain text, easy for
parsing tab-separated tables, and LaTeX. Additionally, the tool generates
colorful plots. All tables and plots are summarized in an interactive HTML
report.

Please [continue here to read the rest](https://docs.google.com/document/d
/10k4vaMPAsFhmBky1Gn-VlrnxbTHR3tGgD9sE1msMp3o/edit).

