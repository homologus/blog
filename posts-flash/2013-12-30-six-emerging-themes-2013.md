---
title: Seven Major Trend Changes of 2013 - (i) Sequencing Technology
tags: []
categories:
- blog
---
This commentary is our modest attempt to capture the essence of over 500 blog
posts published here in 2013. A major trend change is defined as a situation,
where the social perception morphed substantially between the beginning and
the end of 2013.
<!--more-->

**1\. Sequencing Technology - PacBio has Arrived**

Researchers essentially gave up on PacBio technology by the end of 2012. Only
two or three blogs covered it in positive light, ours being one of those. For
example, readers may take a look at our following 2012 posts related to
PacBio.

[HDF5 Data Format for PacBio
Sequences](http://www.homolog.us/blogs/blog/2012/07/06/hdf5-data-format-for-
storing-sequences/)

[Mixing Illumina and PacBio Data for Genome
Finishing](http://www.homolog.us/blogs/blog/2012/08/02/mixing-illumina-and-
pacbio-data-for-genome-finishing/)

[Excellent Slides from Fisherman Lex on Combining PacBio and Short
Reads](http://www.homolog.us/blogs/blog/2012/09/20/excellent-slides-from-
fisherman-lex-on-combining-pacbio-and-short-reads/)

[Basic Local Alignment with Successive Refinement (BLASR) for
PacBio](http://www.homolog.us/blogs/blog/2012/09/19/basic-local-alignment-
with-successive-refinement-blasr-for-pacbio/)

[HGAp Very Accurate de novo Genome Assembly from PacBio
Data](http://www.homolog.us/blogs/blog/2012/11/05/hgap-very-accurate-de-novo-
genome-assembly-from-pacbio-data/)

[PBSIM: PacBio reads simulator](http://www.homolog.us/blogs/blog/2012/11/05/a
-simulator-for-pacbio-reads/).

In contrast, the general perception among scientists was well captured by the
concluding paragraph of a 2012 paper published in BMC Genomics.

[A tale of three next generation sequencing platforms: comparison of Ion
Torrent, Pacific Biosciences and Illumina MiSeq
sequencers](http://www.biomedcentral.com/1471-2164/13/341)

> The limited yield and high cost per base currently prohibit large scale
sequencing projects on the Pacific Biosciences instrument. The PGM and MiSeq
are quite closely matched in terms of utility and ease of workflow. The
decision on whether to purchase one or the other will hinge on available
resources, existing infrastructure and personal experience, available finances
and the type of applications being considered.

Or by this satirical commentary from early 2012.

[A new sequencing technology enters the ring:
SHTseq(TM)](http://pathogenomics.bham.ac.uk/blog/2012/02/a-new-sequencing-
technology-enters-the-ring-shtseqtm/)

>

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
accuracy*.

Fast forward by one year. The experts present at the #UCDAssemble workshop
made the following forecast.

![Capture](http://www.homolog.us/blogs/wp-
content/uploads/2013/12/Capture10-300x51.png)

From 'technology unsuitable for large-scale sequencing projects' to 'the only
thing used to sequence bacterial genomes' is a major shift in perception. Long
reads have definitely arrived.

How did 'extremely noisy' PacBio reads turn out to be useful? Scientists
started to realize that clean short reads also introduced noise through their
short length, and that noise manifested into lower quality of assembly at the
next level of analysis. So, they were trading one form of noise with another.
The following two blog posts explained the above point in detail.

[End of Short-Read Era? (Part I)](http://www.homolog.us/blogs/blog/2013/09/21
/end-illumina-era/)

[End of Short-Read Era? (Part II)](http://www.homolog.us/blogs/blog/2013/09/22
/end-short-read-era-part-ii/)

In other major sequencing technology-related shifts of 2013, [(i) Illumina
acquired Moleculo Inc. for longer read](http://nextgenseek.com/2013/01
/illumina-acquires-molculo-inc-for-longer-reads/), [(ii) Roche closed its 454
sequencing business and announced collaboration with
PacBio](http://www.homolog.us/blogs/blog/2013/10/15/changing-dynamics-
sequencing-world/), [(iii) NabSys unveiled its
instrument](http://www.homolog.us/blogs/blog/2013/02/25/nabsys-unveiled-omics-
omics-blog/) and [(iv) Ion Torrent and BGI announced partnership with BGI
buying 37 new Proton
instruments](http://www.homolog.us/blogs/blog/2013/10/23/proton/).

Nanopore technology in general and Oxford Nanopore in particular continue to
be the wildcards of the sequencing world. Lack of actual sequencing data from
Oxford Nanopore has been a big complaint and the researchers perceive the
company as 'secretive'. Their patent submissions provides some insight into
where the company is heading to.

[Everything You Want to Know about Oxford
Nanopore](http://www.homolog.us/blogs/blog/2013/10/27/everything-want-know-
oxford-nanopore/)

Readers interested in staying ahead of the crowd regarding changing dynamics
of sequencing world are encouraged to follow these excellent blogs.

[Omics! Omics! by Keith Robison](http://omicsomics.blogspot.com/)

[In Between Lines of Code by Lex Nederbragt](http://flxlexblog.wordpress.com/)

[Pathogens: Genes and Genomes by Nick
Loman](http://pathogenomics.bham.ac.uk/blog/author/nick/)

[Opiniomics by Mick Watson](http://biomickwatson.wordpress.com/about/)

\-----------------------------------------------------------------------------
------------------------------------
