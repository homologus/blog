---
title: RapMap - Rob Patro's Reimplements Kallisto's Pseudoalignment Code
tags: []
categories:
- blog
---
If [software license](http://www.homolog.us/blogs/blog/2015/07/10/will-i-use-
kallisto-definitely-most-likely-and-never/) is the only thing that stops you
from using wonderful Kallisto algorithm/program, maybe [this github
code](https://github.com/COMBINE-lab/RapMap/tree/SAQuasiAlignment) can help.
As another advantage, it comes with GPL license (could be BSD if not for
Jellyfish dependence) and you can build your code on top of it by using RapMap
as a module. Pseudoalignment is a powerful lightweight concept and we can
expect more applications to use this module.
<!--more-->

> **What is RapMap?**

RapMap is a testing ground for ideas in lightweight / pseudo / quasi
transcriptome alignment. That means that, at this point, it is very
experimental and there are no guarantees on stability / compatibility between
commits. Eventually, I hope that RapMap will become a stand-alone lightweight
/ pseudo / quasi-aligner that can be used with other tools.

Lightweight / pseudo / quasi-alignment is the term I'm using here for the type
of information required for certain tasks (e.g. transcript quantification)
that is less "heavyweight" than what is provided by traditional alignment. For
example, one may only need to know the transcripts / contigs to which a read
aligns and, perhaps, the position within those transcripts rather than the
optimal alignment and base-for-base CIGAR string that aligns the read and
substring of the transcript.

There are a number of different ways to collect such information, and the idea
of RapMap (as the repository grows) will be to explore multiple different
strategies in how to most rapidly determine all feasible / compatible
locations for a read within the transcriptome. In this sense, it is like an
all-mapper; the alignments it outputs are intended to be (eventually)
disambiguated (Really, it's more like an "all-best" mapper, since it returns
all hits in the top "stratum" of lightweight/pseudo/quasi alignments). If
there is a need for it, best-mapper functionality may be added in the future.

**How fast is RapMap?**

It's currently too early in development for a comprehensive benchmark suite,
but, on a synthetic test dataset comprised of 75 million 76bp paired-end
reads, mapping to a human transcriptome with ~213,000 transcripts, RapMap
takes ~ 10 minutes to align all of the reads on a single core (on an Intel
Xeon E5-2690 @ 3.00 GHz) --- if you actually want to write out the alignments
--- it depends on you disk speed, but for us it's ~15 minutes. Again, these
