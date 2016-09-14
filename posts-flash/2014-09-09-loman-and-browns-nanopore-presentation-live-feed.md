---
title: Nick Loman and Clive Brown's Nanopore Presentation - Live Feed
tags: []
categories:
- blog
---
Tune in at 9AM EST here.
<!--more-->

<iframe width="560" height="315" src="http://www.youtube.com/embed/UtXlr19xTh8" frameborder="0"> </iframe>

Here are some guesses on the technology based on what we are hearing from
everywhere. Those could be good questions to ask.

**1\. Error rate:**

This technology possibly has ~25-30% error rate. We say that based on Michael
Schatz's twitter comment about yeast assembly added [in the previous
post](http://www.homolog.us/blogs/blog/2014/09/09/long-term-direction-of-
nanopore-sequencing-three-ways-from-here/). Typically, all-on-all Pacbio
assembly takes about 50X coverage, whereas Schatz used 100X for his nanopore-
based yeast assembly. We also know from previous talks and discussions that
the errors are from indel.

However, high error rate is not something to be ashamed of, if the technology
delivers sufficiently long reads. In fact, this technology may turn out to be
bioinformaticians' paradise, and they can start all the way from base-calling.
Curious readers may check useful comment by gasstationwithpumps in this post -
[Kalman Filter a Way to Reconstruct Signal from Noisy Data (as in
Nanopore)](http://www.homolog.us/blogs/blog/2013/10/28/kalman-filter-solution-
oxford-nanopores-dilemma/).

**2\. Proper alignment program:**

Apparently BLAST and BLASR are not appropriate alignment programs, but LASTZ
works. How is LASTZ different from the other two programs?

LASTZ was written by R. S. Harris, a PhD student of Webb Miller, who himself
was a collaborator of Eugene Myers. During late 90s, Myers joined Celera,
while Miller became a close collaborator of Ross Hardison to work on, yes you
heard it right, ENCODE. LASTZ was written to align genomes of organisms as
different as human and mouse, and the seeding section of [manual written by Ha
rris](http://www.bx.psu.edu/miller_lab/dist/README.lastz-1.02.00/README.lastz-
1.02.00a.html#options_seeding) gives you the main difference from BLAST/BLASR.

> \--seed=12of19 T=1 or T=2 Seeds require a 19-bp word with matches in 12
specific positions (1110100110010101111).

\--seed=14of22 T=3 or T=4 Seeds require a 22-bp word with matches in 14
specific positions (1110101100110010101111).

Once again, this points to higher than expected error rate. Maybe another good
program exists for aligning those reads, as a cursory reading of homolog.us
blog would suggest. Let us leave at that for the time being :)

**3\. OmicsOmics Blog Reanalyzes Mikheyev/Tin Data**

[Major conclusion](http://omicsomics.blogspot.com/2014/09/reanalysis-lays-
bare-minion-reviews.html) is in bold.

> Summaries of the alignment statistics can be found in Table 2 of Mikheyev &
Tin. For BLASR, they aligned 3.4K (12%) of the 1D reads, for 0.65Mb of bases
aligned to the lambda reference.. This yields a coverage of 13.5X. For 2D, the
statistics aren't much different: 0.9K reads aligned yielding 0.81Mb of
aligned bases. With the LASTAL approach, 8.8K of the 1D reads aligned to yield
33.3Mb of aligned bases. Similarly, for the 2D data, 3.6K reads aligned
yielding 6.6Mb of aligned bases. **So the improved alignment procedures
increased the number of aligned 1D data by about 51X and the amount of 2D data
by about 8.1X.** These numbers are conservative; I kept only the longest
alignment for each read, which precludes some remaining cases in which two
alignments are made which plausibly represent a central region the which
failed to yield an alignment (I do apologize for some different numbers I
tweeted earlier; I let my excitement get the best of me and the 2D number was
quite off).

\---------------------------------------

Full program is here.

> The popular Balti and Bioinformatics series returns, this time in virtual
space! Join us for a nanopore-themed programme which will be streamed from
Google Hangouts to YouTube.

Draft schedule (subject to change)

Times are British Summer Time (GMT+1)

Start: 14:00 BST, 13:00 GMT, 09:00 Eastern Standard Time

14.00 - Intro

14.05 - Clive Brown, Nanopore sequencing

14.45 - Nick Loman, Early data from nanopore sequencing: bioinformatics
opportunities and challenges

15.15 - Matt Loose, Streaming data solutions for nanopore

15.30 - Josh Quick, Nanopore sequencing in outbreaks

15.45 - Torsten Seemann, Awesome pipelines for microbial genomics

16.15 - Finish

