---
title: Next Generation Shotgun Sequencing and the Challenges of de novo Genome Assembly
tags: []
categories:
- blog
---
Through Assemblathon Twitter feed, we came across [a good review
paper](http://www.sajs.co.za/index.php/SAJS/article/viewFile/1256/1499) on NGS
technologies and computational approaches that readers may enjoy. It is
written by S. Schlebusch and N. Illing of Department of Molecular and Cell
Biology, University of Cape Town, Rondebosch, South Africa.
<!--more-->

Few thoughtful observations -

>

SOLiDs advantage of being able to identify single nucleotide polymorphisms
does not make up for its shorter read length which makes the de novo assembly
of complex genomes difficult.

Sequencing on Roches 454 is expensive, but it has a good read length, which is
especially important for the de novo assembly of complex genomes.

Pacific Bioscience has surpassed 454 in read length for a similar cost.

Illuminas platform provides a good balance between read length and cost; and
is the most widely used for such projects.

Paired-end reads on the Illumina or SOLiD platforms are worth the extra cost.

Ion Torrent offers fast sequencing turnover combined with a reasonable read
length; however, the lack of paired-end reads limits it to smaller genomes.

Greedy algorithms should not be used unless computer processing power is
limited and the genome is simple.

With the exception of SGA, the de Bruijn graph programs cope better with the
large numbers of short reads that Illumina or SOLiD will produce.

Having a portion of your coverage as either mate-paired reads or long third-
generation reads will significantly decrease the fragmentation of the final
assembly.

Extreme guanidinecytosine contents can affect the amplification efficiency of
DNA and thus negatively impact second-generation sequencing.

Check to see whether a potential reference genome exists before attempting de
novo assembly (http://www.ncbi.nlm.nih.gov/genome/browse/).

When people compare read lengths, they miss two points -

(i) read quality needs to be taken into account especially when comparing with
PacBio data with 10-15% sequencing noise inherent into the technology. From a
purely statistical view point, we have to reduce effective read sizes of
PacBio reads to get the same informational quality as the noise-free 454
reads. The same holds true for SOLiD data to some extent, when being compared
to Illumina reads.

However, that is not the only adjustment. The cost of bioinformatics should be
another factor of adjustment in real projects. Cost of bioinformatics
essentially made SOLiD less competitive against Illumina, because de Bruijn-
graph based programs for SOLiD were harder to develop than programs for
Illumina. That should not be a factor in a perfect world, but our world is far
from perfect.

(ii) On the topic of read length, people tend to forget that, with paired end
data, conceptually the effective read length is of the entire insert with some
adjustment made for information lost in missing nucleotides in the middle. For
most purposes, Illumina 2x100nt reads can have effective length of 250nt or
more depending on the insert size. This concept was one highlight of the
SPAdes rectangular graph paper that we spoke extensively about.

