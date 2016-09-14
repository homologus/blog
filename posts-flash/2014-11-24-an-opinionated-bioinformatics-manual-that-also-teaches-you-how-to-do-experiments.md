---
title: An Opinionated Bioinformatics Manual that Also Teaches You How to Do Experiments
tags: []
categories:
- blog
---
![Capture](http://www.homolog.us/blogs/wp-
content/uploads/2014/11/Capture8-300x98.png)
<!--more-->

A twitter discussion got us curious about [the manual of the MIRA
assembler](http://mira-
assembler.sourceforge.net/docs/DefinitiveGuideToMIRA.html) and we found it
exactly as promised. The author did a lot of work on helping researchers do
their experiments properly to get high-quality assembly. Bioinformatics does
not work without the 'bio' part done well, and bioinformatics programs cannot
cause miracles, when the underlying data are of bad quality.

Here are two examples out of many informative sections -

>

Warning

For de-novo assemblies, do NOT (never ever at all and under no circumstances)
use the Nextera kit, take TruSeq. The non-random fragmentation behaviour of
Nextera leads to all sorts of problems for assemblers (not only MIRA) which
try to use kmer frequencies as a criterion for repetitiveness of a given
sequence.

>

13.6.1. Do not sample DNA from bacteria in exponential growth phase!

The reason is simple: some bacteria grow so fast that they start replicating
themselves even before having finished the first replication cycle. This leads
to more DNA around the origin of replication being present in cells, which in
turn fools assemblers and mappers into believing that those areas are either
repeats or that there are copy number changes.

Sample. In. Stationary. Phase!

For de-novo assemblies, MIRA will warn you if it detects data which points at
exponential phase. In mapping assemblies, look at the coverage profile of your
genome: if you see a smile shape (or V shape), you have a problem.

This is undoubtedly the most informative bioinformatics manual we came across,
and is way better than many actual papers.

