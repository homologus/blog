---
title: 'Philip Ashton: Assessment of Assembly'
tags: []
categories:
- blog
---
Philip Ashton (@flashton2003 in Twitter) is in the first few months of his
first post-doc as a bioinformatician at Public Health England, and is starting
to write at [Bits and Bugs blog](http://bitsandbugs.org/). He forwarded us an
informative blog post on assessing assembly, where he shows that using N50 as
a sole metric can create too many misassemblies, but give 'better assembly'.
Incidentally, we came to similar realization last year, while using Velvet for
our bootstrapped genome assembly ([What is Wrong with N50? How can we make it
better?](http://www.homolog.us/blogs/2012/06/26/what-is-wrong-with-n50-how-
can-we-make-it-better/), [What is Wrong with N50? How can we make it better?
part II](http://www.homolog.us/blogs/2012/06/26/what-is-wrong-with-n50-how-
can-we-make-it-better-part-ii/)). When we compared k-mer distribution of
assembly with k-mer distribution of reads, we found some k-mers supposed to be
present only once in the genome to be present 7-8 times. That led us to switch
to Minia/SOAPdenovo.
<!--more-->

\-------------------------------------

Cross-posted partly from [Philip's blog](http://bitsandbugs.org/2013/05/02
/velvet-optimiser-vs-kmer-genie/):

## Assessment of Assembly

We, like many people, are interested in optimal de novo genome assembly. When
you assemble a genome you want the best possible representation of the 'true'
genome. How can we obtain the best possible representation?

In the past we have used
[VelvetOptimiser](http://bioinformatics.net.au/software.velvetoptimiser.shtml)
to do our assemblies. This assembles with a range of k-mers and returns the
best assembly. This approach produces assemblies with high N50s, which is a
handy rule of thumb for assembly quality.

However, like the old adage 'as soon as a measure becomes a target, it ceases
to be a valid measure', we are wondering whether optimising for N50 in this
way provides the 'best' assemblies.

So, we decided to assess a couple of different k-mer estimation tools, [Kmer
Genie](http://www.homolog.us/blogs/2013/04/23/informed-and-automated-k-mer-
size-selection-for-genome-assembly/) and
[VelvetK](http://bioinformatics.net.au/software.velvetk.shtml), and see how
assemblies with their K-mers stack up against VelvetOptimiser. The test sample
was paired-end fastq data from a shiga toxin producing _E. coli_ O157 I'm
working on, representative of our samples in terms of coverage and quality.

The three different assemblies were then assessed with
[Quast](http://bioinf.spbau.ru/quast), a reference (I used _E. coli _O157
Sakai) based assembly quality assessment tool.

![Screen Shot 2013-05-02 at
15.27.40](http://bitsandbugsdotorg.files.wordpress.com/2013/06/screen-
shot-2013-06-28-at-13-07-41.png?w=650)

Table 1: Characteristics of the different k-mer estimation tools, calculated
by Quast. Velvet Optimiser k-mer range was 21-121, to match the Kmer Genie
range.

\-----------------------------------------------

Please continue to read the rest [at his
blog](http://bitsandbugs.org/2013/05/02/velvet-optimiser-vs-kmer-genie/). He
included several informative charts and script for you to play with.

