---
title: PacBio Experiences at Norwegian Sequencing Center
tags: []
categories:
- blog
---
[An informative blog](http://flxlexblog.wordpress.com/2013/07/05/de-novo-
bacterial-genome-assembly-a-solved-problem/) post from Lex on PacBio
experience -
<!--more-->

> At the Norwegian Sequencing Centre,with which I am affiliated, we recently
received several bacterial genome DNA samples for PacBio sequencing. Given our
very positive first experiences with size selecting PacBio libraries using the
BluePippin, see my previous post, we decided to use this instrument also for
these samples. Four of the samples yielded very nice libraries, which were
sequenced, two SMRTcells each, on our (recently upgraded) PacBio RSII
instrument.

.....

Wow, mostly one laaarge contig (and I checked, these are without N bases) and
a few shorter ones. The exception was the last strain which assembled into a
few large pieces, that together, according to what I understand, are too
large. A further step for this assembly is trying the Minimus2 tool, to see
whether there is enough overlap between the contigs to further reduce their
number a step generally recommended for HGAp assemblies. I havent tried this
yet for this assembly.

![](https://si0.twimg.com/profile_images/1099225219/DSC01628a_bigger.jpg)

Unlike other bloggers, who leave you with happy/sad/angry feeling, a
moral/immoral/amoral lesson or simply informed/misinformed, Lex leaves you
with a homework :)

> The bottleneck of the HGAp process was the two consensus calling steps: when
the consensus of the longest reads are being called (based on the mapped
shortest ones), and especially for the Celera contig consensus calling. The
latter takes one contig at a time, and since these now are becoming millions
of basepairs long, this can take up many hours, perhaps even half the total
assembly time. By the way, overlapping the error-corrected reads was done in
minutes So, if someone is interested in developing a parallelised consensus
caller, than can work with parts of a long contigs, and stitch the consensi
back together when done, we bioinformaticians doing HGAP would be very
grateful

Enjoy.

