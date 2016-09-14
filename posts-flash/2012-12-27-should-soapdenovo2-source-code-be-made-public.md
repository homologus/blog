---
title: Should SOAPdenovo2 Source Code be Made Public?
tags: []
categories:
- blog
---
During June-July 2012, BGI made its SOAPdenovo2 executable available to the
community, and we reported on how to run it in the following commentaries. Due
to lack of time, we could not provide any benchmarks on how well the assembler
worked compared to other assemblers.
<!--more-->

[Testing SOAPdenovo2 Pre-release
Version](http://www.homolog.us/blogs/2012/06/27/testing-soapdenovo2/)

[Testing SOAPdenovo2 Pre-release Version II
(pregraph_sparse)](http://www.homolog.us/blogs/2012/07/04/testing-soapdenovo2
-pre-release-version-part-ii/)

[Testing SOAPdenovo2 Prelease Version
III](http://www.homolog.us/blogs/2012/07/05/testing-soapdenovo2-prelease-
version-iii/)

[Testing SOAPdenovo2 Prerelease IV (building
contigs)](http://www.homolog.us/blogs/2012/07/05/testing-soapdenovo2
-prerelease-iv-building-contigs/)

[Testing SOAPdenovo2 Prerelease V (map and
scaff)](http://www.homolog.us/blogs/2012/07/10/testing-
soapdenovo2-prerelease-v-map-and-scaff/)

[SOAPdenovo2: an empirically improved memory-efficient short-read de novo
assembler](http://www.gigasciencejournal.com/content/1/1/18/abstract)

Readers interested in such comparison may take a look at the SOAPdenovo2 paper
that just came out at the [GigaScience
website](http://www.gigasciencejournal.com/content/1/1/18/abstract). However,
for a better comparison, you will have to wait for the Assemblathon 2 paper
that is currently being written.

>

**Background**

There is a rapidly increasing amount of de novo genome assembly using next-
generation sequencing (NGS) short reads; however, several big challenges
remain to be overcome in order for this to be efficient and accurate.
SOAPdenovo has been successfully applied to assemble many published genomes,
but it still needs improvement in continuity, accuracy and coverage,
especially in repeat regions.

**Findings**

To overcome these challenges, we have developed its successor, SOAPdenovo2,
which has the advantage of a new algorithm design that reduces memory
consumption in graph construction, resolves more repeat regions in contig
assembly, increases coverage and length in scaffold construction, improves gap
closing, and optimizes for large genome.

**Conclusions**

Benchmark using the Assemblathon1 and GAGE datasets showed that SOAPdenovo2
greatly surpasses its predecessor SOAPdenovo and is competitive to other
assemblers on both assembly length and accuracy. We also provide an updated
assembly version of the 2008 Asian (YH) genome using SOAPdenovo2. Here, the
contig and scaffold N50 of the YH genome were ~20.9 kbp and ~22 Mbp,
respectively, which is 3-fold and 50-fold longer than the first published
version. The genome coverage increased from 81.16% to 93.91%, and memory
consumption was ~2/3 lower during the point of largest memory consumption.

Sbastien Boisvert, who is an expert on genome assembly, commented about lack
of availability of source code of SOAPdenovo2 in his blog commentary.

[The source code of SOAPdenovo2 sits in the shadows
](http://dskernel.blogspot.ca/2012/12/the-source-code-of-soapdenovo2-sits-
in.html)

> Concern #1: ELF 64-bit LSB executables for GNU/Linux 2.6.9 are not platform-
independent. Therefore, the claim of platform independence is false. For
instance, I can not run these executables on OpenBSD.

Concern #2: GCC version ? 4.5.0 is not required as it is a proprietary binary
distribution. Therefore this requirement is untrue.

Concern #3: proprietary software distributions are not eligible to licensing
under the GNU General Public License version 3. Therefore, the authors should
select their own proprietary license or release the source code of
SOAPdenovo2. The previous last publicly available version was SOAPdenovo
v1.05.

Peter Cock went one step further in arguing that the paper should not have
been accepted given that the source code was not available.

![Capture](http://www.homolog.us/blogs/wp-
content/uploads/2012/12/Capture4-300x73.png)

What do you think? Is it always customary to release source code on
publication of a bioinformatics paper, or is it enough to discuss the
algorithm?

