---
title: Oxford Nanopore Keeps Falling Behind
tags: []
categories:
- blog
---
A new paper on bacterial genome assembly titled ["A single chromosome assembly
of Bacteroides fragilis strain BE1 from Illumina and MinION nanopore
sequencing data"](http://biorxiv.org/content/early/2015/08/11/024323) has been
submitted to biorxiv. The senior author is Mick Watson, an [academia-based
vocal promoter of the company](http://www.homolog.us/blogs/blog/2015/06/18
/oxford-nanopore-fans-are-asking-three-questions-today/). Therefore the paper
likely shows the state-of-the-art of the technology.
<!--more-->

The most puzzling observation one can make from the paper is the discrepancy
between the claimed and the actual error rate of nanopore sequences. We
recently had this discussion with David Eccles, who wrote in the comment
section - "The median error per base was approximately 7% for this run (i.e.
93% accuracy)". Similar claims of 92%-93% accuracy had been made by other
Nanopore promoters. If that is true, the obvious follow-up question would be -
why does Mick Watson (and many others) need to use Illumina reads to assemble
bacterial genomes? For Pacbio reads with 85% accuracy, one can easily assemble
bacterial genomes from Pacbio-only.

The answer lies in two 'details'. (i) For Pacbio reads, 85% accuracy is before
processing, whereas Oxford nanopore reads appear to go through rounds of
processing to get to 92%. I pointed that out to David Eccles [in the comment
section](http://www.homolog.us/blogs/blog/2014/10/19/nanopore-updates-from-
david-eccles/#comment-129638). (ii) The second and more important point is
that the error distribution of Pacbio reads is completely random, thus making
compensation through high coverage possible. We are not sure what the error
distribution of Oxford nanopore reads is. It is possibly not random given that
they continue to need support from Illumina sequences for genome assembly.

The hybrid assembly argument vouched in the following abstract was the status
quo for Pacbio one year back, but based on my recent conversation with the
members of Pacbio community, those researchers are increasingly moving away
from using any Illumina read. Apparently, those short reads seem to complicate
the assembly process instead of helping. They were useful, when Pacbio reads
were expensive, but will not be any more.

> **Background**

Second and third generation sequencing technologies have revolutionised
bacterial genomics. Short-read Illumina reads result in cheap but fragmented
assemblies, whereas longer reads are more expensive but result in more
complete genomes. The Oxford Nanopore MinION device is a revolutionary mobile
sequencer that can produce thousands of long, single molecule reads.

**Results**

We sequenced Bacteroides fragilis strain BE1 using both the Illumina MiSeq and
Oxford Nanopore MinION platforms. We were able to assemble a single chromosome
of 5.18 Mb, with no gaps, using publicly available software and commodity
computing hardware. We identified gene rearrangements and the state of
invertible promoters in the strain.

**Conclusions **

The single chromosome assembly of Bacteroides fragilis strain BE1 was achieved
using only modest amounts of data, publicly available software and commodity
computing hardware. This combination of technologies offers the possibility of
ultra-cheap, high quality, finished bacterial genomes.

\-----------------------------------

Edit.

Sam Minot pointed out Jared Simpson's work on E. coli assembly from Oxford
nanopore only, which we covered
[here](http://www.homolog.us/blogs/blog/2015/02/20/e-coli-genome-assembled-
using-nanopore-data-only/)\-

![Capture](http://www.homolog.us/blogs/wp-
content/uploads/2015/10/Capture2-300x97.png)

It is puzzling that despite that earlier success, others are not adopting
similar approach, given that assembling from Oxford nanopore only would be the
biggest selling point for the company. It does not make sense to talk about
carrying USB-sized sequencer to the field, if one also has to carry a large
Illumina instrument. There are two possible explanations for Mick Watson's not
using Simpson's algorithm/program - (i) he is not aware of it, (ii) he is
unable to make it work.

Other helpful twitter comment -

![Capture](http://www.homolog.us/blogs/wp-
content/uploads/2015/10/Capture3-300x55.png)

![Capture](http://www.homolog.us/blogs/wp-
content/uploads/2015/10/Capture4-300x105.png)

