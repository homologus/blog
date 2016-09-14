---
title: Large Computer, Distributed Cluster or Amazon Cloud?
tags:
- computer
- RAM
categories:
- blog
---
[A very popular comment in seqanswers
forum](http://seqanswers.com/forums/showthread.php?t=4589) starts with -
<!--more-->

> **Hello - I use to think I was good with a computer**

I wonder how many people are in the same boat as me.

1) Institute bought a couple of GAIIs

2) No one has money to use them

3) Institute has internal competition to pay for a couple of runs (makes the
donors feel better about their donation if someone uses the machines), and you
are lucky enough to get funded

4) You send a couple of samples off to never-never land and someone sends back
a terabyte drive or two with "next-gen sequencing data"

5) You quickly realize people that use to do survival curves in your
bioinformatics core don't really know that Illumina fastq is different from
Sanger fastq and the analysis they provide is limited at best

5) Now what do you do?

Everyone working with NGS data can relate to the above experience. Some of us
are perpetually in that boat, because not only the volume of NGS data is
growing exponentially, the [rate is higher than growth of computing
power](http://ivory.idyll.org/blog/aug-11/cloud-not-the-solution.html).

Typically, the first step is to get access to a computer that can handle large
volumes of data. That is also when the head starts spinning with various
choices - Should we buy a high-RAM computer and put it in my basement? Should
we build a multi-node cluster? Should we move to the 'cloud'? Today we present
opinions from various experts.

Blogger Jermdemo suggests getting a 'big ass server' in his comment titled
[Big-Ass Servers and the myths of clusters in
bioinformatics](http://jermdemo.blogspot.com/2011/06/big-ass-servers-and-
myths-of-clusters.html).

>

From an economic and productivity perspective, I believe most bioinformatics
shops doing basic research would benefit more from having access to a BAS than
a cluster. Here's why:

* The development of multicore/multiprocessor machines and memory capacity has outpaced the speed of networks. NGS analyses tends to be more memory-bound and IO-bound rather than CPU-bound, so relying on a cluster of smaller machines can quickly overwhelm a network.

* NGS has forced the number of high-performance applications from BLAST and protein structure prediction to doing dozens of different little analyses, with tools that change on a monthly basis, or are homegrown to deal with special circumstances. There isn't time or ability to write each of these for parallel architectures.

The rest of his article is very informative, and I suggest you check it out.

That 'big ass server' is not going to be cheap. Professor Titus Brown provides
some numbers in ["How much compute power do you need for next-gen
sequencing?"](http://ivory.idyll.org/blog/jul-11/how-much-compute-ngs.html)

>

In summary:

Hard disk: $5000/yr (not counting RAID, NAS, permanent backups, etc.)

Compute: approx. 8 medium computers, $40,000/yr (not counting air
conditioning)

Memory: 1x bigmem computer minimum, $50,000/yr (not counting air conditioning)

\---

The numbers above feel OK to me, but may be a little bit light. If I was doing
nothing other than running such a center, I'd want about double that (so
figure $100-200k/year, hardware costs), which would result in a fair amount of
overcapacity that others could use. But if I had to give the minimum budget,
$100k/year for preliminary sequence analysis sounds about right.

On his blog, Professor Brown has several helpful articles about cloud
computing. I found the following comment interesting from his article [The sky
is falling! The sky is falling!](http://ivory.idyll.org/blog/oct-10/sky-is-
falling.html) \-

>

As Narayan has eloquently argued many times, it no longer makes sense for most
institutions to run their own HPC, if you take into account the true costs of
power, AC, and hardware. The only reason it looks like HPCs work well is
because of the way institutions play games with funny money (a.k.a. "overhead
charges"), channeling it to HPC behind the scenes - often with much
politicking involved. If, as a scientist, your compute is "free" or even
heavily subsidized, you tend not to think much about it. But now that we have
to scale those clusters 10s or 100s or 1000s of X, to deal with data 100s or
1e6s of times as big, institutions will no longer be able to afford to build
their own clusters with funny money. And they'll have to charge scientists for
the true computational cost of their work -- or scientists will have to use
the cloud. Either way, people will be exposed to how much it really costs to
run, say, BLAST against 100,000,000 short reads. And soon thereafter they'll
stop doing such foolish things.

Please let me know, if you see other helpful comments on the above topic.

