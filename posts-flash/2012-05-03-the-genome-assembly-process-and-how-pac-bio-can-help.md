---
title: The Genome Assembly Process and How Pac Bio can Help
tags:
- Pac Bio
categories:
- blog
---
After playing with the Pac Bio data for a while, we figured out how to make
the best use of it in our assembly pipeline. I am posting something I wrote
for a collaborator, in case it helps others. I would also recommend you to go
through the links at the bottom of my previous commentary. [The slides from
Michael Schatz](http://schatzlab.cshl.edu/presentations/2011-09-07.PacBio%20Us
ers%20Meeting.pdf) are particularly helpful.
<!--more-->

> To understand the assembly process, you need to visualize an eukaryotic
genome. The simplest picture consists of a linear chain of unique regions
joined by repeat/low complexity regions. Unique regions appear only once in
the genome. Repeat regions appear many times in the genome. We can add other
complications like haplotype difference to the above simple picture later, but
they are secondary for most genomes.

The assembly process has three steps -

i) Assemble all pieces of unique regions. These are called contigs.

ii) Connect them up. The end product is called scaffold.

iii) Fill in the gaps in between with repetitive sequences.

The first step is relatively easy with Sanger reads, but gets complicated with
Illumina reads. It is generally accepted as the most difficult step in a
short-read assembly process. One needs to be careful about an aggressive
assembler that connects pieces which should not be connected. The possibility
of making this kind of error goes up, when the reads are short.

The second step is equally challenging, whether you have Sanger or Illumina
reads. Basically, you link up various short fragments using mate pairs, multi-
exon genes, and anything else you can find.

The third step is often not completed, when a genome paper is published. For
example, if you download rat or cow genomes published several years back, you
will find that the genomes were filled with NNNNNN sequences. Those NNNNNN
regions represent unassembled repeats. The assembler made an estimate about
how big the repeat is, but could not manage to fill up the repeats.

Let me give you some numbers about how a genome looks like at the publication
stage. I am most familiar with the sea urchin genome, which has roughly 900Mb
of nucleotides. When it was published, the genome contained 114K pieces
(scaffolds). Three years after publication, Baylor released an update, where
they brought down the number of pieces to 32K. The pieces are not all of equal
size, and N50 is the most accepted statistics to judge the quality of the
assembly.

As it appears to me, Pac Bio data is not good for de novo assembly of unique
regions, unless you have tons of sequences. Illumina seems to be more well-
suited. However, PacBio can be of tremendous help in joining the unique
regions.

If you compare Pac Bio (5Kb reads) with Illumina 5Kb mate pairs for the
purpose of joining reads, one big advantage of Pac Bio is that it also gives
you the intermediate sequences. So, not only we connect up two fragments, we
also get what is in between. However, one big caution here is that the
connection made with Pac Bio will be 'noisy', whereas the Illumina contigs
being connected contain high-quality data. Therefor, one needs to make the Pac
Bio reads go through error-correction process (typically using Illumina) to
turn them into good sequences.

