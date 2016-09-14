---
title: New Blog Post from Gene Myers on "Intrinsic Quality Values" of Pacbio Sequences
tags: []
categories:
- blog
---
We like to alert our readers about a new blog post from Gene Myers on assembly
of Pacbio reads. In it, Myers wrote about his frustration with incorporating
quality scores coming out the machines -
<!--more-->

> I tried every way I could think of to aggregate these Q-scores over a say
100bp interval so as to arrive at an informative statistic about the overall
quality of that 100bp stretch and failed.

After using a new method to analyze 'regional read piles",

(

> Hopefully, the examples and exposition above make it clear that analyzing
read piles is pretty interesting and informative.

)

he concluded -

> It is a matter of experience, but my general finding is that of the QVs not
capped at 50, about 80% of the data is definitely usable and 5-7% is
definitely bad, leaving the rest in a grey zone.

\-----------------------------------------------------------------------------

[Intrinsic Quality Values - Gene
Myers](https://dazzlerblog.wordpress.com/2015/11/06/intrinsic-quality-values/)

> One of the most vexing problems with Pacbio data is that it is very
difficult to understand the quality of a given small segment or region of a
read. The Q-scores that come out of the instrument are not particularly
informative in this regard, their value seems to be mostly in indicating if a
given base is better or worse than the bases neighboring it (and this is of
importance to multi-aligners and consensus callers like Quiver). I tried every
way I could think of to aggregate these Q-scores over a say 100bp interval so
as to arrive at an informative statistic about the overall quality of that
100bp stretch and failed. But having this information is very important
because over the course of a long 10-40Kbp read, the quality of the base calls
varies significantly, where there are even long internal stretches that are
essentially junk. I illustrate a typical Pacbio read error profile to help you
further understand why I think it is extremely important to understand the
regional quality of a read.

[Continue reading](https://dazzlerblog.wordpress.com/2015/11/06/intrinsic-
quality-values/)

