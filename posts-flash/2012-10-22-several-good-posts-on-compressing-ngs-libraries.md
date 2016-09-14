---
title: Several Good Posts on Compressing NGS Libraries
tags: []
categories:
- blog
---
Compressing NGS libraries for storage, transmission and efficient analysis is
an important issue. We covered the topic some time back in a commentary titled
[Quip, Minia, SlimGene and Titus Browns paper on Scaling
Metagenome](http://www.homolog.us/blogs/2012/07/19/quip-minia-slimgene-and-
titus-browns-paper-on-scaling-metagenome/). Readers may like to take a look at
several interesting discussions on the same issue.
<!--more-->

1\. C. Titus Brown: [Compressing next-gen sequencing data, and the next
sequence squeeze competition](http://ivory.idyll.org/blog/sequence-
squeezing.html)

2\. Ewan Birney: [DNA Compression: Reprise
](http://genomeinformatician.blogspot.co.uk/2012/05/dna-compression-
reprise.html)

3\. Ewan Birney: [Engineering around reference based compression
](http://genomeinformatician.blogspot.co.uk/2011/05/engineering-around-
reference-based.html)

4\. Katil Malde: [Compressing biological
sequences](http://blog.malde.org/posts/compressing-biological-sequences.html)

Papers:

1\. The following paper showed a way to compress NGS libraries using BWT.

[Large-scale compression of genomic sequence databases with the Burrows-
Wheeler transform](http://bioinformatics.oxfordjournals.org/content/early/2012
/05/02/bioinformatics.bts173.abstract)

2\. [SCALCE: boosting Sequence Compression Algorithms using Locally Consistent
Encoding ](http://bioinformatics.oxfordjournals.org/content/early/2012/10/08/b
ioinformatics.bts593.full.pdf+html)

\------------------------------------------

Take home messages from the above links:

** A. Compression is very important**

Ketil commented in [CTB's blog](http://ivory.idyll.org/blog/sequence-
squeezing.html):

> Is the data sizes really such a big deal? Currently, the cost of Illumina
sequencing is about 1000x the cost of storage, which in turn is about the same
as the cost of computational power for mapping/analysis. If sequencing tech
continues to evolve at faster rates than computers then eventually it will be
a problem, but currently I think it isn't worth bothering with.

Please check CTB's thoughtful reply, but in our mind, the economic case for
compressing NGS libraries is clear.

Storage: When we expect data to live for ever (>> lifetime of a hard-disk),
the storage cost is much higher than the price of a single hard-disk, and is
closer to the storage fees of cloud systems.

Accessible storage: If the only purpose of doing the experiment were to lock
up hard-drives of data in a safe deposit box, that would brought down the
storage cost a lot. The cost of making data readily accessible means we now
invest in faster hard-drive, redundancy, etc.

Bandwidth: This is possibly the biggest bottleneck right now, and the cost
adds up every time a new user wants to download all NGS raw reads to assemble
a version of human genome.

Analysis: Mapping is not the only type of analysis. Given how fast the field
is evolving, it is foolhardy to limit options of a future user by guessing
what the data is useful for and remove everything else.

**B. FASTQ Quality Score is the biggest Problem in Reducing File Sizes**

Solution - Get rid of qual scores at the earliest chance.
[Here](http://edwards.sdsu.edu/labsite/index.php/bas/309-converting-fastq-to-
fasta-and-qual) is the script.

Yes, we know you were expecting to hear something more intelligent. The answer
is in Ewan Birney's commentary linked above. Bottom line - FASTQ quality score
carries lot more 'quality information' than is informative. As an analogy, if
someone gives you a bad scale to measure your weight and you come up with
71.237144917 kg, most digit on the right side are meaningless. Why not
compress the weight to 71.2 kg and save space?

C. **Sequence-based Compression is the Hottest Idea**

Regular compression methods such as gzip, zip, etc. do not use domain
knowledge and therefore are not likely to produce the best compression. One
possible way to do better is to assemble reference sequence in some way and
use it to compress. We already discussed the method in the context of Quip.

\-------------------

Few of our own observations:

**1\. All Discussions are Limited to Illumina data**

We have not seen much discussion on what to do with large SOLiD or PacBio
libraries, whose compression based on reference may not be as easy as Illumina
data due to inherent noisiness in the data. Do we clean their reads and only
store cleaned version? Will storage of cleaned data be acceptable by the
community?

**2\. Do we compress to recover raw reads or recover biology?**

The method to find optimal compression will see push-pull from two aspects -
(i) are we compressing to recover raw reads as faithfully as possible, or (ii)
are we compressing to recover biological aspects of reads as faithfully as
possible? We do not think there is an easy answer, and sacrifices need to be
made.

**3\. Sequencing is Becoming Cheap and so We Need not be Stuck with 'Expensive Sequencing' Mindset**

Some of the conservativeness of the community described in Birney's commentary
come from their mindset getting stuck in an earlier era of biology, when
sequencing was expensive and it was important to save as much as possible.
Cheap sequencing is the primary cause of data deluge, but cheap sequencing
also allows us to reproduce experiments lot more easily than in earlier days.
That consideration will tilt the scale towards 'compressing to reproduce
biology' from 'compressing to reproduce raw reads' in point 2.

