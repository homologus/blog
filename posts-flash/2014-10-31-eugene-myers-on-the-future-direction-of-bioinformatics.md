---
title: Eugene Myers on the Future Direction of Bioinformatics
tags: []
categories:
- blog
---
Now that it has become rather inexpensive to sequence and assemble genomes,
transcriptomes and metagenomes, the question is what to do with this
advancement in technology. The conventional answer is to sequence as much as
you can in various 1k, 10k and 100k genome/transcriptome/x-ome project fashion
and ask questions later. This mentality led to abundance of GWAS (Genome Wide
Association Studies) to determine 'causal variants' for all kinds of human
traits. The approach failed despite inflated claims and media splash about
dramatic discoveries, and the big claims were rightly criticized by
knowledgeable scientists. For example, check the following two blog posts by
Ken Weiss and Dan Graur -
<!--more-->

[The height of folly: are the causes of stature numerous but at least
'finite'?](http://ecodevoevo.blogspot.com/2014/10/the-height-of-folly-are-
causes-of.html)

[DisGWASted Again: Another #GWAS, Another Diddly Squat Accompanied by Loud
Fanfare](http://judgestarling.tumblr.com/post/100610791666/disgwasted-again-
another-gwas-another-diddly-squat)

Despite criticisms, the backers of GWAS and 'more sequencing' continue to
claim - (i) the failure is due to small sample size, whereas their efforts
will be successful with even more data, (ii) there is no alternative.

In a series of three posts ([here](http://www.homolog.us/blogs/blog/2014/08/11
/bioinformatics-at-a-crossroad-again-which-way-next/),
[here](http://www.homolog.us/blogs/blog/2014/09/02/crossroads-ii-is-it-too-
late-to-acknowledge-that-systems-biology-and-gwas-failed/) and
[here](http://www.homolog.us/blogs/blog/2014/10/14/crossroads-iii-a-new-
direction-for-bioinformatics-with-twelve-fundamental-problems/)), we showed
that both claims were wrong. Borrowing from a paper by Sydney Brenner, we
argued that GWAS and systems biology type of methods would not work due to
flaws in fundamental scientific reasoning, whereas the alternative is to make
cells, and not the genome, the center of attention. We also proposed a set of
fundamental problems in biology and urged bioinformaticians to focus on
solving those problems instead of building new tools for better genome
assembly.

![Gene_Myers_ISMB_2014](http://www.homolog.us/blogs/wp-
content/uploads/2014/10/Gene_Myers_ISMB_2014.jpg)

Speaking of developing genome assembly algorithms and other bioinformatics
techniques, if one person had always been way ahead of time, that was Eugene
Myers. In most core algorithm related to sequence alignment or assembly, you
will find his significant contribution and he made those contributions in
early 1990s ! He was the brain behind the company Celera, which was the first
to sequence a human genome.

We sought opinion from Eugene Myers about our (and Brenner's) suggestion about
focusing on cells instead of the genome and he kindly replied -

> I read the article and I pretty much concur. I work at an institute trying
to understand development in terms of what *cells* can do, and I am dedicated
to analyzing images and movies of what things encoded in the genome do in
cells.

Let us add a bit more information to explain the above comment. Most
bioinformaticians noticed that Myers took a break from sequence-related work
since 2006-2007, right around the time when NGS took off. The conventional
wisdom would say that he probably missed the trend, but those knowing his past
record finds that he was again building the future way ahead of others. In
2009, his group worked with Stuart Kim to publish this interesting paper on C.
elegans. This work brought forward Sydney Brenner's work on C. elegans to the
high-throughput age, and Myers' group added the missing piece - computational
identification of images of cells.

[Analysis of Cell Fate from Single-Cell Gene Expression Profiles in C.
elegans](http://www.cell.com/cell/abstract/S0092-8674\(09\)01118-0)

> The C. elegans cell lineage provides a unique opportunity to look at how
cell lineage affects patterns of gene expression. We developed an automatic
cell lineage analyzer that converts high-resolution images of worms into a
data table showing fluorescence expression with single-cell resolution. We
generated expression profiles of 93 genes in 363 specific cells from L1 stage
larvae and found that cells with identical fates can be formed by different
gene regulatory pathways. Molecular signatures identified repeating cell fate
modules within the cell lineage and enabled the generation of a molecular
differentiation map that reveals points in the cell lineage when developmental
fates of daughter cells begin to diverge. These results demonstrate insights
that become possible using computational approaches to analyze quantitative
expression from many genes in parallel using a digital gene expression atlas.

More details are available [here](http://www.mpi-cbg.de/research/research-
groups/gene-myers.html) \-

>

**Exploring Cells & Systems via Image Analysis and Customized Microscopy 

**

We are best known for BLAST and the whole-genome shotgun protocol and
assembler accomplishments in traditional sequence-based bioinformatics. But
since 2002 the group has focused almost exclusively on analyzing and
extracting information from images obtained by various forms of microscopy. We
believe that such data will reveal more about the function of the entities
encoded in the genome then any other approach and will eventually become a
prevailing paradigm of investigation, like sequence-based discovery is today.
The group has even begun to develop its own customized microscopes.

Since 2002 we have worked on the following representative problems among
others:

Building a cell model of a C.elegans L1 larvae and software to automatically
extract cell-by-cell expression levels in situ.

Building models of the fly nervous system using light microscopy. By
stochastically expressing GFP in every individual neuron in this brain, we
expect to deliver a detailed view of the highly stereotyped neuronal
connectivity of the fly brain.

Tracking and measuring the vibrissae of a mouse while it is performing a
cognitive function.

Tracking microtubules and centrosomes during the first few cell divisions of
the embryogenesis of C. elegans.

Construction of an ultra-fast, block-face multi-photon microscope with onboard
microtome for imaging a mouse brain with 1/2-micron pixels in less than a
week.

In broad terms, the computational challenges are to build canonical 3D models
of biological systems and map molecular observations onto the model. That is,
there is the challenge of registering observations from different animals into
a single representative framework, and the challenge of extracting meaningful
information in the presence of low SNR and diffraction-limited resolution. The
offsetting factor to low SNR and resolution is the presence of very strong
prior knowledge about the morphology and dynamics of the entities under
observation. Many of our new techniques thus involve what are called template-
driven approaches.

We are in essence a technology group. Our aim is to develop microscopes and
software that make observations of in situ and in vivo systems that enable our
collaborative partners to advance molecular and cellular biology. We have
worked closely with Stuart Kim (Stanford), Chris Doe (Oregon), Tony Hyman
(MPI-CBG), Karel Svoboda, Gerry Rubin, Jim Truman, and Tzumin Lee (HHMI JFRC)
as examples. The figure below illustrates imagery from three of our projects.

The overarching goal of our group is to build optical devices, collect
molecular reagents, and develop analysis software to monitor in as much detail
as possible the concentration and localization of proteins, transcripts, and
other entities of interest within a developing cohort of cells for the purpose
of working together with other groups in the Dresden area towards a
biophysical understanding of development at the level of cell communication
and force generation.

![](http://www.mpi-cbg.de/uploads/pics/s_myers.png)

