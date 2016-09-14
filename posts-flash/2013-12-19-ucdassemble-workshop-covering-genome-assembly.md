---
title: " #UCDAssemble Workshop Covering Genome Assembly"
tags: []
categories:
- blog
---
Readers interested in sequence assembly may take a look at the tweets under
hashtag [#UCDAssemble](https://twitter.com/search?q=%23UCDAssemble&src=hash&f=
realtime). It is attended by a number of researchers, who are working on
writing genome assembly programs or are heavy users of such programs (e.g.
Jared Simpson, Jason Chin, Titus Brown, Lex Nederbragt, Nick Loman). The
workshop is technically-oriented with a number of hands on exercises. We will
summarize the key points for those without twitter access.
<!--more-->

Conference-related documents are available [here](http://davis-assembly-
masterclass-2013.readthedocs.org/en/latest/index.html).

\-------------------------------------

**How to Pronounce de Bruijn?**

The conference started with answering the most pressing issue of the day -
saying de Bruijn correctly. Following twitter comments have the answer:

![Capture](http://www.homolog.us/blogs/wp-
content/uploads/2013/12/Capture7-300x100.png)

There is also a [Biostar thread](http://www.biostars.org/p/7186/) on the same
topic.

\---------------------------------------

**Quality Assessment and Adapter Trimming**

Jared Simpson discussed his preqc software for quality check before genome
assembly. [We covered it](http://www.homolog.us/blogs/blog/2013/07/02/cool-
preprocessing-model-for-genome-assembly/) a few months back.

Nick Loman pointed out about the importance of adapter-trimming. His blog post
on this topic is linked below.

[Adaptor trim or die: Experiences with Nextera
libraries](http://pathogenomics.bham.ac.uk/blog/2013/04/adaptor-trim-or-die-
experiences-with-nextera-libraries/)

Other programs mentioned in the same context -

[Kraken for discovering adaptor sequences de
novo](http://www.ebi.ac.uk/research/enright/software/kraken)

[Coral: an error correction algorithm for reads from platforms such as the
Illumina or Roche/454](http://www.cs.helsinki.fi/u/lmsalmel/coral/)

\----------------------------------------

**Kitomics from Nick Loman**

Nick Loman pointed out that the kits themselves can be contaminated and need
to be sequenced before actual sample.

![Capture2](http://www.homolog.us/blogs/wp-
content/uploads/2013/12/Capture21-300x239.png)

\---------------------------------------

**PacBio Makes a Big Stir**

The workshop organizers arranged a number of talks on PacBio and they seemed
to have left a positive impression on the technology.

Shane Brubaker:

Following tweets cover his presentation.

![pacbio1](http://www.homolog.us/blogs/wp-
content/uploads/2013/12/pacbio1-300x146.png)

"Brubaker: Haplotyping algorithm available for PacBio #UCDAssemble"
[Link](https://github.com/hsiaut/readUntangler)

Jason Chin:

Jason Chin presented on diploid assembly. He made his slides available.

Lex Nederbragt:

Lex Nederbragt presented on the cod assembly.

** [Improving and validating the Atlantic Cod genome assembly using PacBio](https://www.slideshare.net/flxlex/131120-pac-biousermeetinglondon) ** from **[Lex Nederbragt](http://www.slideshare.net/flxlex)**

Lawrence Hon:

We did not see too many tweets and presume he presented on how to assemble
using HGAP. Title of talk - "Larger genome hybrid assembly with PacBio.

Brett Bowman:

Presented on a metagenome data set that PacBio releases for public
consumption. Relevant tweets are below.

![Capture](http://www.homolog.us/blogs/wp-
content/uploads/2013/12/Capture9-300x278.png)

The biggest hit appears to be string-graph visualization software from
@infoecho (Jason Chin).

**Too many Programs, Too Little Benchmarking**

Lex Nederbragt pointed out the biggest difficulty faced by bioinformaticians
today. It is not abundance of data or lack of computers, but publication of
too many programs, each claiming to be doing better than others. Someone needs
to rescue bioinformatics world from Lake Wobegon, where "all the children are
above average", and that means the dirty work of benchmarking !

**Blobology**

Attendees discussed Sujai Kumar's Blobology approach. Those unfamiliar with
the word can check his recent paper and get started.

[Blobology: exploring raw genome data for contaminants, symbionts, and
parasites using taxon-annotated GC-coverage
plots](http://www.frontiersin.org/Journal/10.3389/fgene.2013.00237/abstract)

> Generating the raw data for a de novo genome assembly project for a target
eukaryotic species is relatively easy. This democratization of access to
large-scale data has allowed many research teams to plan to assemble the
genomes of non-model organisms. These new genome targets are very different
from the traditional, inbred, laboratory-reared model organisms. They are
often small, and cannot be isolated free of their environment whether ingested
food, the surrounding host organism of parasites, or commensal and symbiotic
organisms attached to or within the individuals sampled. Preparation of pure
DNA originating from a single species can be technically impossible, but
assembly of mixed-organism DNA can be difficult, as most genome assemblers
perform poorly when faced with multiple genomes in different stoichiometries.
This class of problem is common in metagenomic datasets that deliberately try
to capture all the genomes present in an environment, but replicon assembly is
not often the goal of such programs. Here we present an approach to
extracting, from mixed DNA sequence data, subsets that correspond to single
species genomes and thus improving genome assembly. We use both numerical
(proportion of GC bases and read coverage) and biological (best-matching
sequence in annotated databases) indicators to aid partitioning of draft
assembly contigs, and the reads that contribute to those contigs, into
distinct bins that can then be subjected to rigorous, optimized assembly,
through the use of taxon-annotated GC-coverage plots (TAGC plots). We also
present Blobsplorer, a tool that aids exploration and selection of subsets
from TAGC-annotated data. Partitioning the data in this way can rescue poorly
assembled genomes, and reveal unexpected symbionts and commensals in
eukaryotic genome projects. The TAGC plot pipeline script is available from
https://github.com/blaxterlab/blobology, and the Blobsplorer tool from
https://github.com/mojones/Blobsplorer.

