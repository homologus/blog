---
title: Minia 2.0.1 is Released
tags: []
categories:
- blog
---
Long-term readers probably remember Minia by Rayan Chikhi et al., one of the
most memory-efficient contig assembler from short reads. We first mentioned it
[here](http://www.homolog.us/blogs/blog/2012/07/19/quip-minia-slimgene-and-
titus-browns-paper-on-scaling-metagenome/) and then analyzed the code in this
post - [Minia Assembler and French
Revolution](http://www.homolog.us/blogs/blog/2012/10/01/minia-assembly-
algorithm-and-french-revolution/). Minia later got reincorporated into [GATB
library](http://www.homolog.us/blogs/blog/2014/07/16/minias-new-home-gatb-
genome-assembly-analysis-tool-box/).
<!--more-->

Rayan [recently announced](https://www.biostars.org/p/129849/) in biostar
about releasing Minia and DSK 2.x.x.

> Minia is a low-memory short-read assembler for large genomes. It creates
contigs.

DSK is a low-memory k-mer counter.

We have ported Minia and DSK to a new codebase that uses the GATB library. To
make the change clear, from now on, Minia and DSK using the new codebase will
have versions 2.x.x.

New features:

Minia 2.0.1, [http://minia.genouest.org](http://minia.genouest.org/)

Faster (multi-core parallelism)

Slightly more accurate (has coverage information in the graph, for better
discrimination between sequencing errors and polymorphism)

Less disk usage (because of DSK)

Can output unitigs

DSK 2.0.1, <http://minia.genouest.org/dsk>

Faster (multi-core parallelism)

Less disk usage

comparable performance to KMC2 (we're using their techniques :)

Download (Linux 64 bits):

Minia: http://gatb-tools.gforge.inria.fr/versions/bin/minia-2.0.1-Linux.tar.gz

DSK: http://gatb-tools.gforge.inria.fr/versions/bin/dsk-2.0.1-Linux.tar.gz

For legacy, the final versions of Minia and DSK 1.xxx (old codebase) are
http://minia.genouest.org/files/minia-1.6906.tar.gz and
http://minia.genouest.org/dsk/dsk-1.6906.tar.gz .

However we recommend using the 2.x.x versions, as results are expected to be
identical (in the case of DSK) or slightly better (Minia), while 2.x.x
performance is significantly better (2x-4x) than 1.xxx versions.

You might be tempted to reply to this post in case you find a bug, or an
installation problem, etc... But please make a new Biostar post instead:

[Post a question / bug report regarding
Minia](https://www.biostars.org/p/new/post/?tag_val=minia)

[Post a question / bug report regarding
DSK](https://www.biostars.org/p/new/post/?tag_val=dsk)

For a recent user review of Minia, please check -

[Genome Assembly without the
RAM](https://rmcsoftwareinc.wordpress.com/2015/02/04/genome-assembly-without-
the-ram/)

Assembling genomes with little memory.

> De novo assembly is the construction of genomes without reference to
existing known genomes. There is a wide variety of de novo assembly tools
available for constructing genomes. Its well-known that many of these tools
require substantial amounts of memory for assembling large genomes. For these
assemblers the definition of large genome usually refers to something greater
than about 1 Gb (gigabase, 1B nucleotides), although there are genomes that
exceed this length by a considerable amount.

From experience we know that some assemblers require several hundred GB
(gigabytes) up to 1 TB (terabyte) of RAM, per compute node, in a cluster
computing environment, in order to assemble large genomes. This can be very
expensive. Therefore, were evaluating a relatively new de novo assembler,
Minia, as an alternative to some of the traditional assemblers. Apparently,
Minia can assemble human scale genomes with about 5 GB RAM. Lets see what our
evaluation discovered.

 [Continue reading](https://rmcsoftwareinc.wordpress.com/2015/02/04/genome-
assembly-without-the-ram/)

