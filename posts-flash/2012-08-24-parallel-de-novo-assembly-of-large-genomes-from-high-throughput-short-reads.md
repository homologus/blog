---
title: Parallel de novo Assembly of Large Genomes from High-Throughput Short Reads
tags: []
categories:
- blog
---
We have been going through [an interesting paper by Srinivas Aluru's
group](https://agora.cs.illinois.edu/download/attachments/35490033/IPDPS-
aluru.pdf) on parallel implementation of String Graph Assembler for NGS reads.
<!--more-->

B. D. Jackson in Dr. Aluru's group has been working on parallel implementation
of string graph assembler for a while, but their papers do not seem to get
cited by mainstream bioinformaticians possibly due to their lack connections
with sequencing centers. However, we are familiar with Dr. Aluru's name for
[his significant contribution to NGS bioinformatics](http://scholar.google.com
/scholar_url?hl=en&q=http://citeseerx.ist.psu.edu/viewdoc/download%3Fdoi%3D10.
1.1.83.9781%26rep%3Drep1%26type%3Dpdf&sa=X&scisig=AAGBfm09mia3pPKaMXxrXJw1bvjb
CkWvWQ&oi=scholarr) even before NGS was born.

The paper of genome assembler is a bit mathematical, but that should not deter
you from trying to figure out what they are doing. For those truly interested
in deconvoluting the mathematical description should start with B. G.
Jackson's PhD thesis
[here](http://archives.ece.iastate.edu/archive/00000503/01/thesis.pdf).

The following references may also be helpful, but we have not gone through
them yet -

B.G. Jackson and S. Aluru. Parallel construction of bidirected

string graphs for genome assembly. In Proc. 37th International

Conf. on Parallel Processing, pages 346353, 2008.

B.G. Jackson, P.S. Schnable, and S. Aluru. Assembly of large

genomes from paired short reads. In Proc. 1st International

Conference on Bioinformatics and Computational Biology,

volume 5462, pages 3043, 2009.

B.G. Jackson, P.S. Schnable, and S. Aluru. [Parallel short

sequence assembly of transcriptomes. BMC Bioinformatics,

10:S14, 2009.

