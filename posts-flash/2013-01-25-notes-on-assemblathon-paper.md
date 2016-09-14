---
title: Notes on Assemblathon Paper
tags: []
categories:
- blog
---
Note. Please check here for various commentaries on [Assemblathon
paper](http://assemblathon.org/feedback-and-analysis-of-the-assemblathon-2-p).
<!--more-->

\-----

Over the last two days, we have been going through the Assemblathon-2 paper
and its supplements carefully, and here is what we learned so far. The
following text is not a coherent discussion of the paper, but rather an
assortment of mostly unrelated comments.

**End of Velvet Era**

In Assemblathon-1, many teams used Velvet as their primary assembler. This
time, we hardly see it mentioned.

**Number of Independent Assemblers**

At first, we were excited to find out that Baylor's assemblies competed well
and thought that they developed another kick-ass assembly program we can start
parsing in the coming months. Then we realized that they used ALLPATHS-LG as
the contig assembler, and their own Atlas-Link and Atlas-GapFill for
scaffolding and gap-filling steps. Overall, three assemblers - AbySS,
ALLPATHS-LG and SOAPdenovo2 dominated the landscape and were used by multiple
groups. Other assemblers - Phusion, Ray, Meraculous, Newbler, Celera and SGA
were used primarily by their developers. Also, the French Symbiose team
developed a set of assembly tools that competed very well. Wish they gave an
unique name to the package for marketing purpose :)

The above observation about mixing of assembly tools opens up an interesting
challenge for anyone trying to interpret the results. Let us say Broad
Institute, Baylor, CSHL and University of Georgia all used ALLPATHS-LG for
their assemblies and ranked differently in the contest. Does that mean
ALLPATHS-LG is a good and a lousy assembler at the same time? Or does it mean
the associated tools used by four groups were of different quality? Or is the
assemblathon measuring competence of teams and not qualities of automated
assembly tools?

**Cost of Genome Assembly**

Fish genome (1 Gb) had 192x coverage from 8 Illumina HiSeq libraries. The
library cost is ~$15-20K.

For assembly cost, we can play with numbers from various teams. Here is the
one from Ray -

>

Computational requirements

Version: 32 computers, 8 cores per computer, 24 GB RAM per computer. Approx.
running time: 3672 hours (depending on species).

Machine cost ~ $32000.

Energy requirement for computers - 60 hours x 1 kwh/machine x 32 = 1920 kwh

At 20c/kwh, energy cost = $384/assembly

We exclude cooling cost for computing center, which is expected to add the
base energy cost.

Are we doing the calculation correctly? Does an user run multiple assemblies
to pick up the best one, or is the 36-72 hours inclusive of all iterations?

Given that fish genome is 1/3 the size of human genome, does it cost
$384*3=$1152 in energy to assemble human genome?

There are other costs for storing sequences, high-speed internet, etc. that we
neglected here. What is the real cost of automated assembly of mammalian
genome after all costs are accounted for?

**Mirror Mirror on the Wall, Who Is the Fairest of Them All**

Biggest contribution of Assemblathon paper is likely their list of metrics to
judge the qualities of assemblies.

> 1\. NG50 scaffold length: a measure of average scaffold length that is
comparable between different assemblies (higher = better).

2\. NG50 contig length: a measure of average contig length (higher = better)

3\. Amount of scaffold sequence gene-sized scaffolds (>= 25 Kbp): measured as
the absolute difference from expected genome size, this helps describe the
suitability of an assembly for gene finding purposes (lower = better).

4\. CEGMA, number of 458 core genes mapped: indicative of how many genes might
be present in assembly (higher = better).

5\. Fosmid coverage: calculated using the COMPASS tool, reflects how much of
the VFRs were captured by the assemblies (higher = better).

6\. Fosmid validity: calculated using the COMPASS tool, measures the amount of
the assembly that could be validated by the VFRs.

7\. VFR tag scaffold summary score: number of VFR tag pairs that both match
the same scaffold multiplied by the percentage of uniquely mapping tag pairs
that map at the correct distance apart. Rewards short-range accuracy (higher =
better).

8\. Optical map data, Level 1 coverage: a long-range indicator of global
assembly accuracy (higher = better).

9\. Optical map data, Levels 1+2+3 coverage: indicates how much of an assembly
correctly aligned to an optical map, even if due to chimeric scaffolds (higher
= better).

10\. REAPR summary score: rewards short- and long-range accuracy, as well as
low error rates (higher = better).

**What will happen in Assemblathon-3?**

Assemblathon-3 is possibly the last thing in the minds of various genome
assembly teams after finishing this major paper, but is there a need for
Assemblathon-3? We believe there should not be any Assemblathon-3. Instead,
the next step should be to completely dismantle various assembler programs
into smaller units, and explain why they performed the way they did by mixing
and matching various components from competing assemblers.

**Spammer's paradise**

Here is something funny. When we opened the Assemblathon-2 paper, the first
thing that came to our mind was that email spammers would have a field day
with so many email addresses given together. I guess it is just the cost of
doing business :)

