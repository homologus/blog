---
title: New Bioinformatics Business Model - Make Software Free, Charge for Manual
tags: []
categories:
- blog
---
@Assemblathon forwarded a new paper [BLESS: Bloom-filter-based Error
Correction Solution for High-throughput Sequencing Reads](http://bioinformatic
s.oxfordjournals.org/content/early/2014/01/21/bioinformatics.btu030.short?utm_
content=buffer71ce3&utm_medium=social&utm_source=twitter.com&utm_campaign=buff
er)
<!--more-->

> Motivation: Rapid advances in next-generation sequencing (NGS) technology
have led to exponential increase in the amount of genomic information.
However, NGS sequencing reads contain far more errors than data from
traditional sequencing methods, and downstream genomic analysis results can be
improved by correcting the errors. Unfortunately, all the previous error
correction methods required a large amount of memory, making it unsuitable to
process reads from large genomes with commodity computers.

Results: We present a novel algorithm that produces accurate correction
results with much less memory compared to previous solutions. The algorithm,
named BLESS, uses a single minimum sized Bloom filter and is also able to
tolerate a higher false positive rate, thus allowing us to correct errors with
a 40X memory usage reduction on average compared to previous methods.
Meanwhile, BLESS can extend reads like DNA assemblers to correct errors at the
end of reads. Evaluations using real and simulated reads showed that BLESS
could generate more accurate results than existing solutions. After errors
were corrected using BLESS, 69% of initially unaligned reads could be aligned
correctly. Additionally, de novo assembly results became 50% longer with 66%
fewer assembly errors.

Availability: Freely available at http://sourceforge.net/p/bless-ec

That seemed interesting and we were curious about how different their approach
is from Rayan Chikhi or Titus Brown's work. Sadly, when we wanted to see the
actual paper, we were greeted with this wonderful page.

![Capture0](http://www.homolog.us/blogs/wp-
content/uploads/2014/01/Capture0-300x191.png)

\-----------------------------------------------------------------------------
-------------------
---------------
