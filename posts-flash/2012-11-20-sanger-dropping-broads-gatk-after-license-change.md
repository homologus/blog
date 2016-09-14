---
title: Sanger Dropping Broad's GATK after License Change
tags: []
categories:
- blog
---
A battle over open-source versus closed-source started in another front of the
bioinformatics world. Broad Institute's popular GATK 1.0 tools were released
under open source agreement, but apparently [they are not interested in doing
the same](http://storify.com/pjacock/gatk-v2-0-not-open-source) with GATK 2.0.
That makes Sanger Institute rethink its use of GATK 2.0 [as reported by Mick
Watson](https://twitter.com/BioMickWatson/status/268364030173929472).
<!--more-->

What do they plan to use then? Here are various answers.

> Peter Cock ?@pjacock: Perhaps Sanger are considering making a fork of the
#opensource GATK v1 code base, and continue to develop that?

> Mick Watson ?@BioMickWatson: work with and develop samtools

> Thomas Keane ?@drtkeane: I wasn't speaking for all of Sanger but yea
planning more focused dev of samtools & HTSlib

Other bioinformaticians complaints about not being able to fix bugs due to
closed source nature of GATK. We note that, SOAPdenovo, BGI's popular sequence
assembly tool, is not open source either.

We expect more and more tools to go closed-source, when government money for
academic research dries out. Who said fighting endless wars around the world
would be cost-free?

\---------------

Without going into the philosophical debates between open-source versus
closed-source, we can see Broad's decision from the point of view of the
developers. A smart developer will make his program closed-source, if he sees
long-term economic advantage in keeping the code under wrap. A smart developer
will make his program open-source, if he sees long-term economic advantage in
releasing the code.

**What kind of thoughts support hiding of the code?**

**Answer**: a team of programmers, who are well ahead of others, and have market demand for their product, can easily argue in favor of hiding the code. Hiding the code gives them economic advantage over others, because open-source competitors need to - 

(i) figure out their algorithm,

(ii) develop competing code,

(iii) find sustainable economic system (donations, grants, etc.) to support
their programming.

In the meanwhile, those who are ahead and have strong user-base can easily
make their code open and foil efforts of competitors.

**What kind of thoughts support releasing the codes?**

(i) Grant-supported researchers usually release their code in public to gain
more acceptance/visibility for their work and thus more grants.

(ii) Organizations, who are behind the leaders, can make their code open-
source to find free help from potential users or to make a selling point
against their financially flush competitors. [Example: MySQL]

(iii) Small software companies sometimes release one lesser version of their
code under open-source, while make another sophisticated version closed-
source. It is an intelligent marketing approach to sell software over the
internet. [Example: [Fusioncharts](http://www.fusioncharts.com/goodies
/fusioncharts-free/)]

Did we miss something?

