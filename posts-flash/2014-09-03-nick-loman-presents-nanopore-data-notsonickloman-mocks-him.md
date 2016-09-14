---
title: 'Nick Loman Presents Nanopore Data, #NotsoNickLoman Mocks Him'
tags: []
categories:
- blog
---
Finally some real data are coming out on Oxford Nanopore and the technology
appears to be very promising. Readers are encouraged to take a look at the
summary of tweets from Nick Loman's presentation on sequencing of E. coli
genome -
<!--more-->

[Nick Lomans Talk on Nanopore Sequencing Using MinION at
#UKGS2014](http://nextgenseek.com/2014/09/nick-lomans-talk-on-nanopore-
sequencing-using-minion-at-ukgs2014/)

Key points -

1\. "After 72 hour run (48 is standard), total reads approached 45,000
(277,353,019 bp)."

2\. "Nanopore can run for up to 60 hours with topping up of reagents, giving
277 Megabp; has won 3/10 weeks on yield."

3\. Mean read length 6,069 bp, median 5,204 bp. Fairly long tail to
distribution (up to 40 Kbp).

4\. No regions left unsequenced in E. coli genome.

On read quality, it appears that each read is expected to have considerable
noise similar to PacBio reads, although it is not clear whether noise
distribution is uniform. One possibility is to use hybrid assembly with clean
short Illumina reads and dirty long Nanopore reads.

Overall, we find this to be an incredible technology given that the sequencer
is hand-held and can be used in many remote locations. However,
bioinformatician #NotsoNickLoman did not like the last part about noisy data
and posted a mocking commentary in his blog.

[A new sequencing technology enters the ring:
SHTseq(TM)](http://pathogenomics.bham.ac.uk/blog/2012/02/a-new-sequencing-
technology-enters-the-ring-shtseqtm/)

>

Just received this press release from Neil Hall, CEO of a new sequencing
company called CrapBio whos launching at this years #notAGBT.. sounds very
interesting!

**CrapBio**

CrapBio is excited to announce the release of its new SHTseq whole genome
sequencing platform which is going to revolutionize the genomics industry and
soon the healthcare industry.

**Longer Reads-Better Data noSHT (What would you do with 100Mb reads?).**

We are able to generate super-long reads with our ARSesnsors. Using CrapBio-
SHTseq technology we regularly get 10Mb reads and we have even seen reads of
100Mb which completely sequenced E. coli 20 times in a single read. Our base
calling accuracy is 25%, but with genomes with extreme AT/GC bias it reaches
40%. Although this is lower than other platforms the longer reads allow you to
extract much more information from our reads than old-fashioned 2nd generation
sequencers. Also this error is totally randomly distributed (unlike
homopolymer errors in other technologies!) and there is no decline in base
calling accuracy toward the ends of reads. The last base in a read is just as
good as the first base.

**Cleaning up SHT with Illumina data**

If, for whatever reason, you need accurate sequence data we have developed
hybrid assembler that can incorporate Illumina error correcting reads. With
our HybridAssemblyReadDenoisingSHT data you can simply upload you 100x
illumina data with your sample and get reads returned to you will 99.999%
accuracy*

We condemn all such attacks on mighty nanopore :)

