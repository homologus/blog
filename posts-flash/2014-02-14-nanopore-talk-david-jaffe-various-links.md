---
title: Nanopore Talk by David Jaffe - Various Links
tags: []
categories:
- blog
---
Unlike others, who are disappointed by the first presentation of Oxford
Nanopore data today, we feel excited. Why? It is because now we can move
beyond all kinds of speculations regarding what miracles nanopore sequencing
will achieve and focus on actual science of data quality, noise reduction
algorithms, reconstruction and realistic road-map. Also, we can discuss the
merits of competing technologies by Oxford Nanopore, Quantum Bioscience,
PacBio and maybe even Moleculo (reconstructed long read), if getting long
reads is the real goal.
<!--more-->

The blog nextgenseek covers all tweets from David Jaffe's talk in storified
version.

[A First Look at the Use Oxford Nanopore Reads AGBT
2014](http://nextgenseek.com/2014/02/a-first-look-at-the-use-oxford-nanopore-
reads-agbt-2014/)

Allseq blog presented a nice summary of the talk reconstructed from
tweetstreams.

[A view of AGBT from afar](http://www.allseq.com/blog/a-view-of-agbt-from-
afar)

>

Operational specs:

Mostly what weve heard before there are 512 nanopores/cm2 (on the MinION) and
each pore can read sequence at a rate of 1-100 bps (the presented dataset was
run at 25 bps). The new thing was the read profile of overlapping 6mers
-presumably meaning that 6 bases at a time occupy the nanopore.

Read length:

In the presented dataset the average read length with 5kb, with some reads up
to 20kb. Those are nice long reads, but not that impressive in the face of
what PacBio is doing these days. It was stated that the read length was
limited by the quality of the sample and that longer reads will be possible
with better quality samples or more careful prep. This is in line with what
weve heard from PacBio prep is now the limiting factor for read length.
(However, it should be noted that Nabsys seems to not have a problem getting
>100kb reads.)

Quality:

The read quality seems to have an unusual profile. There are stretches of
perfect reads (84% of >5kb reads have at least a perfect 50mer and 100% have
at least a perfect 25mer) that are interrupted by error-blocks that appear to
be systematic artifacts. These error-blocks are dominated by indels, mostly
deletions. ONT is working on improving this through the use of multiple pore
types (which presumably will have non-overlapping error profiles).

Lex Nederbragt also chimed in.

[The one and only Oxford Nanopore talk at AGBT 2014 with real
data](http://flxlexblog.wordpress.com/2014/02/14/the-one-and-only-oxford-
nanopore-talk-at-agbt-2014-with-real-data/)

>

Here are a few of my thoughts about this presentation. On its own, this is a
fantastic breakthrough for nanopore based DNA sequencing. Not earlier has a
nanopore platform been able to show this kind of data. So, congratulations are
in place for Oxford Nanopore.

The lengths of reads presented may seem disappointing given the presentation
at AGBT two years ago, where 100 kbp reads were mentioned. However, the limit
may have been the size distributions after fragmentation. As users of the
PacBio platform know, fragmentation is an art for obtaining long reads, so
there is a clear potential for improvement here.

The error-model, which seems to be biased and systematic, is worrying from an
assembly and variant calling point of view. It will probably improve over
time. On the other hand, there are, as Jaffe eluded to, lots of applications
where having (near)-perfect reads are not crucial. Think scaffolding,
structural variation detection, isoforms for RNA (cDNA) sequencing, etc.

There remain a few open questions, though. Nothing was mentioned on coverage
of the genomes sequenced (a clear miss by Jaffe). Hopefully, there will be no
GC bias, for example. A careful look at the errors is needed, for example, are
there chimeric reads, adaptors present, long-range errors in the reads?

What about the comparison with other long-read platforms? The data presented
is somewhat similar to moleculo data in terms of length, with a lower quality
and a yet-to-be determined GC bias. PacBio reads are significantly longer, and
of a better quality after self error-correction. The big difference is of
course price. A PacBio instrument, and a HiSeq, are very much more expensive
than the MinION. A small USB stick also takes up much less space, and can be
carried around to the field, especially if library prep can be made small
enough.

Erika Check Hayden of Nature wrote -

[Oxford Nanopore unveils data from portable genome sequencer
](http://www.nature.com/news/oxford-nanopore-unveils-data-from-portable-
genome-sequencer-1.14724)

>

MinION results are promising, but fall short of high expectations.

.....

Jaffe also found that the MinION appeared to have difficulty sequencing
particular parts of the bacterial genomes that he studied. That is worrisome
to bioinformaticians, because it is more challenging to correct for systematic
sequencing errors than random ones. In Jaffe's case, the recurring errors
prevented him from assembling the complete genome sequences of the two
bacteria from scratch using only MinION data; instead, he used MinION
sequences to supplement data generated by Illumina machines.

Yet he sounded an optimistic note about the MinION's future. Oxford has said
that higher-quality DNA or different preparation methods should increase the
average read length. Jaffe says that the company can work to eliminate errors,
perhaps by using a mix of pores with different properties. But even now, he
says, the vast majority of long MinION reads had lengthy stretches without any
mistakes. The systematic errors are a temporary feature that we hope they'll
figure out how to solve.

Other researchers will soon have a chance to form their own opinions about the
new device, as Oxford today launched its early-access programme. Researchers
who pay a US$1000 deposit, plus $250 for shipping costs, can receive MinIONs
on which they can run their own experiments.

