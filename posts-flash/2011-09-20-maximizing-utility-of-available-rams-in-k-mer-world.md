---
title: Maximizing Utility of Available RAMs in K-mer World
tags:
- de-bruijn
- transcriptome assembly
- K-mer
- genome assembly
categories:
- blog
---
[somewhat unedited]
<!--more-->

Bioinformaticians trying to assemble genomes or transcriptomes from large NGS
libraries usually grapple with two problems - (i) how to set parameters to get
the best assembly, and (ii) how to complete the assembly within RAM limits of
the computer. Reaching limits of available RAM is always a challenge with
large sequence libraries, no matter how powerful our computers are. The
simplest solutions are either to remove a random subset of reads or trim reads
from their 3' ends on an ad hoc basis. Are they optimal? More sophisticated
versions of above solutions are to remove duplicate reads instead of random
reads, or to use quality scores for trimming ends of the reads. Are multiple
copies of a read really redundant to the de Bruijn assemblers? We believe the
researchers need to reorient themselves to k-mer world view to design most
optimal cleaning strategies.

Let us say you intend to do a genome assembly from 200 million reads in a
computer with 128 GB RAM. The amount of RAM is insufficient for your computer,
and therefore you need to cut down on the input library size. Conceptually
everyone understands that keeping the best reads and removing the worst ones
would produce the best result. It is just that the reads do not come marked
with good or bad except for the quality score from the sequencers, but the
quality scores are not always helpful for small errors.

Let us handle the problem in a different way. We shall plot the distribution
of k-mers in the data, and show that the distribution has two parts - signal
and noise. The goal of best cleaning strategy is to reduce noise and keep
signal Why do we check the k-mers? Because that is how de Bruijn assemblers
view the sequence data.

If you remember our earlier discussion on de Bruijn graphs, we [first
constructed de Bruijn graph of a
genome](http://www.homolog.us/blogs/2011/07/28/de-bruijn-graphs-i/) and [then
showed](http://www.homolog.us/blogs/2011/07/29/de-bruijn-graphs-ii/) that de
Bruijn graph constructed from short reads is nearly identical to the de Bruijn
graph of the underlying genome. In this discussion, we will follow similar
approach, but instead of going all the way to de Bruijn graphs, we shall
restrict ourselves to the K-mers only.

In the following chart, we present the 21-mer distribution of sea urchin
(_Strongylocentrotus purpuratus_) genome. The genome is approximately 900
Mbase long. To prepare this chart, we first split both strands of the genome
into all possible 21-mers, and then collected the 21-mers into groups. Most
21-mers were unique in the genome, i.e. they were present only once. Those are
21-mers from non-repetitive parts of the genome. To give you an exact number,
994,401,729 21-mers were present only once in the genome. That is the number
you see for x=1 in the following graph. 122,161,264 21-mers were present twice
(x=2). 20,077,544 21-mers were present thrice (x=3). So, x axis of the
following chart shows multiplicity of 21-mers and y axis shows total count for
that multiplicity in the sea urchin genome. At the other end of the curve,
10,000 21-mers were present 67 times in the genome. Those were the repeat
regions.

![](http://www.homolog.us/blogs/wp-content/uploads/2011/09/urchin-real-
300x300.png)

In the next exercise, we created simulated short reads (100-mer) by sampling
the genome uniformly. The reads had 50X coverage on the genome, but all reads
were error-free. Here is the K-mer distribution of the short reads generated
in the same way as the above plot. Please note that Y-axis in the following
plot is scaled down.

![](http://www.homolog.us/blogs/wp-content/uploads/2011/09/urchin-sim-
300x300.png)

We see a large peak at x=40 instead of x=1. What does it mean? By way of
construction, every part of the genome is sampled nearly 50 times. A subset of
those short reads (about 20%) fell on repetitive regions. Therefore, the
unique regions of the genome were sampled 40 times. So, every K-mer that was
present once in the genome is now present about 40 times in the short read
library.

You also see a smaller peak at 80. That comes from those K-mers that were
present 2 times in the genome. In fact, we checked and found out that the
ratio of the peak size at 80 and peak size at 40 in the simulated read data is
equal to the ratio of peak size at 2 and peak size at 1 in the K-mer
distribution of the genome.

In the next figure, we show the K-mer distribution constructed from short read
library of another genome that we are trying to assemble. This is real data
from 100 nucleotide Solexa libraries (HiSEQ), not simulated data.

![](http://www.homolog.us/blogs/wp-content/uploads/2011/09/eel-real-
300x300.png)

You see a peak at around 55 suggesting that the short reads sampled the unique
parts of the genome 55 times as expected from simulated data. However, you
also see a large peak near 1. That is noise.

![](http://www.homolog.us/blogs/wp-content/uploads/2011/09/Capture-
300x278.png)

Why is the noise peak so big? Think about this - every time a read has one
nucleotide error, it can result in 21 erroneous 21-mers. Thus, when we look at
the k-mer distribution of all reads, errors appear magnified k times. However,
there is also memory cost to having those errors, because Each of those
erroneous k-mer occupies an unique space in the computer memory. Therefore,
much of the RAM is actually wasted by the erroneous k-mers rather than real
k-mers.

Clearly, a good strategy for cleaning data would be to reduce the noise peak
as much as possible. When we trim 3' edges, it makes sense to check what
trimming is doing to the noise peak. If cutting one additional nucleotide does
not reduce amount of noise, it is not helping the assembly. I think checking
the k-mer distribution is a better measure than using the pre-assigned quality
scores from the sequencer.

Removing duplicate reads reduces the size of signal peak compared to noise
peak, and therefore it is a bad strategy. If one is keen on removing fraction
of reads, he should try to find the reads that give rise to faulty k-mers and
remove them. That step will also result in far better memory usage than
removing duplicate reads.

