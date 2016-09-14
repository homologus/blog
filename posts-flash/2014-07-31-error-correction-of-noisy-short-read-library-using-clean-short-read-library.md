---
title: Error-correction of Noisy Short Read Library using Clean Short-read Library
tags: []
categories:
- blog
---
A biologist working on exotic vertebrate organisms asked:
<!--more-->

> I am looking for a program that does error correction for short reads, and
more specifically one that can use one dataset to generate a list of trusted
kmers and then use that list to perform error correction on a second dataset.
We have shotgun sequencing data and data from single chromosomes that have
been picked and amplified. The amplified material has some systematic error
that we would like to get under control. We've tried to mix data from
amplified libraries with WGS data and run error correction on the whole set
using RACER, but this just generates a mess and the reads seem to be less
accurate than before correction.

Just like he was looking for trusted kmers, I had to get a reply of his
question from a number of trusted experts, who all chimed in. The replies are
posted in the order they came in.

[Anton Korobeynikov](http://anton.korobeynikov.info/):

> I'm not aware about any tool which would work in such a mode out of the box.

Few notes (wearing my BayesHammer developer hat):

1\. As far as I can read from RACER paper - it can only be used for

multi-cell datasets. Basically it uses coverage threshold to deduce

whether a k-mer is good or not. Certainly, this won't work on

amplified datasets.

2\. It may happen that BayesHammer would work on the data your

collaborator has out of the box

3\. If not - it fairy easy to modify BayesHammer to support the mode

your collaborator wants

[Heng Li](http://en.wikipedia.org/wiki/Heng_Li):

> For fermi/fermi2, you can build the FM-index for one set of reads and use
this FM-index to correct another set of reads.

[Jared Simpson](http://bioinformatics.ca/person/cbw-core-faculty/jared-
simpson):

> SGA can do this as well.

[Mark Chaisson](https://eichlerlab.gs.washington.edu/mchaisso.html):

> And if you want to resurrect the dead, the EULER-SR error correction may be
supplied any table of solid tuples for error correction, so you have plenty to
choose from, though I'd recommend Jared or Heng's programs.

Resident non-expert:

The way I would do is to get a kmer-profile from both batches and then compare
distributions to see which kmers are present in unusual count. That way, I can
figure out whether the 'systematic error' is in making some reads noisy or in
amplifying some parts of the genome. If the problem is in the second, some
kind of method to remove duplicate paired end reads should help. Check [this
biostar thread](https://www.biostars.org/p/2733/) for example. If the
systematic error is in changing the reads, only then k-mer based error
correction can be useful.

\-----------------------------------------------

I just noticed that the original question had a part 2. Is what he plans to do
(correcting one library with another) a bad idea? Please feel free to let us
know what you think. I am a bit uncomfortable with the idea unless the
biologist can make sure that he is only correcting for errors and not getting
rid of signal in the process. Possibly a profiling and comparison between
error-corrected and original reads will help.

