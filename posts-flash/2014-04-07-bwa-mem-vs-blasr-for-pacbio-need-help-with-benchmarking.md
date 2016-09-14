---
title: BWA-MEM vs BLASR for PacBio - Need Help with Benchmarking
tags: []
categories:
- blog
---
A few months back, we posted -
<!--more-->

[Is BWA-MEM as Good as BLASR for Aligning PacBio Reads? Part
1](http://www.homolog.us/blogs/blog/2013/10/23/bwa-mem-blasr-look-pacbios-
newly-released-human-data/)

[Is BWA-MEM as Good as BLASR for Aligning PacBio Reads? Part
2](http://www.homolog.us/blogs/blog/2013/10/28/bwa-mem-good-blasr-aligning-
pacbio-reads-part-2/)

Those commentaries were about using BWA-MEM, Heng Li's new long-read aligner,
to align PacBio reads. Although Heng did not have PacBio in his mind in
writing the code, we noticed many similarities between the algorithms of BWA-
MEM and BLASR. After comparing the two methods, we found out that BWA-MEM
indeed aligned Pacbio reads much faster than BLASR, but on the negative side,
the matches were somewhat fragmented.

\----------------------------------------------------------------------

Today, we have two pieces of good news for our readers.

i) Heng Li got interested in tuning BWA-MEM to align PacBio reads. He found a
set of BWA MEM parameters that minimize the fragmentation of alignments. The
updates are not yet integrated in the main BWA code and he needs help with
benchmarking.

Here is how to run the PacBiofied BWA-MEM.

>

Checkout the github HEAD and run bwa-mem on PacBio reads with:

bwa mem -x pacbio ref.fa reads.fa

ii) Mark Chaisson, the author of BLASR, also made a number of updates to the
BLASR code to make it run much faster than earlier. The changes are not
integrated into the official version that PacBio yet.

If you are interested in comparing the speed and accuracy of BWA-MEM vs BLASR,
please feel free to comment here on what you find, and both Heng and Mark will
be very happy. You can use the official version of BLASR for the time-being,
until we hear back from Mark/PacBio on integrating Mark's latest changes.

Here are the optimal settings for using BLASR (from Mark) -

> For human I use -bestn 2 -maxAnchorsPerPosition 100 -advanceExactMatches 10
-affineAlign -affineOpen 100 -affineExtend 0 -insertion 5 -deletion 5 -extend
-maxExtendDropoff 20 . The -bestn 2 is to detect larger structural
rearrangements with downstream code.

\-------------------------------------------------------------------

Needless to add that after these warm-up work, Heng will most likely go after
updating his recent arxiv paper to incorporate the library released by PacBio.

[How Noisy Are Those Variant Calls from Short Reads
Really?](http://www.homolog.us/blogs/blog/2014/04/04/how-noisy-are-those-
variant-calls-from-short-reads-really/)

> As we were writing up this work, Paci?c Biosciences released deep
resequencing data for the CHM1 cell line. It could be used to isolate errors
caused by the Illumina sample preparation and sequencing. However, mapping and
variant calling from PacBio human data is still in the early phase. We decided
to leave out the comparison to the PacBio data for now.

