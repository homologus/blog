---
title: Assemblathon 2 Paper is Available at Arxiv !!
tags: []
categories:
- blog
---
Notes.
<!--more-->

1\. Please check here for various commentaries on [Assemblathon
paper](http://assemblathon.org/feedback-and-analysis-of-the-assemblathon-2-p).

2\. Please follow [this link](http://arxiv.org/abs/1301.5406). Supplements are
available [here](http://korflab.ucdavis.edu/Datasets/Assemblathon/Assemblathon
2/Additional_files/).

\-----------------------

**Assemblathon 2: evaluating de novo methods of genome assembly in three vertebrate species**

> Background - The process of generating raw genome sequence data continues to
become cheaper, faster, and more accurate. However, assembly of such data into
high-quality, finished genome sequences remains challenging. Many genome
assembly tools are available, but they differ greatly in terms of their
performance (speed, scalability, hardware requirements, acceptance of newer
read technologies) and in their final output (composition of assembled
sequence). More importantly, it remains largely unclear how to best assess the
quality of assembled genome sequences. The Assemblathon competitions are
intended to assess current state-of-the-art methods in genome assembly.

Results - In Assemblathon 2, we provided a variety of sequence data to be
assembled for three vertebrate species (a bird, a fish, and snake). This
resulted in a total of 43 submitted assemblies from 21 participating teams. We
evaluated these assemblies using a combination of optical map data, Fosmid
sequences, and several statistical methods. From over 100 different metrics,
we chose ten key measures by which to assess the overall quality of the
assemblies.

Conclusions - Many current genome assemblers produced useful assemblies,
containing a significant representation of their genes, regulatory sequences,
and overall genome structure. However, the high degree of variability between
the entries suggests that there is still much room for improvement in the
field of genome assembly and that approaches which work well in assembling the
genome of one species may not necessarily work well for another.

Within the text, here is an important paragraph. To an outsider, it may read
like 'we do not have any clue, which assembler is the best'. However, when you
read the entire paper, you will realize that it is because the qualities of
all assemblers have come up so much that it is hard to call any one of them a
clear winner. Only in case of snake, SGA stands out. Another observation -
fish genomes were incredibly hard to assemble.

>

**Lessons learned from Assemblathon 2**

The clear take-home message from this exercise is the lack of consistency
between assemblies in terms of interspecific as well as intraspecific
comparisons. An assembler may produce an excellent assembly when judged by one
approach, but a much poorer assembly when judged by another. The SGA snake
assembly ranked 1st overall, but only ranked 1st in one individual

key metric, and ranked 5th and 7th in others. Even when an assembler performs
well across a range of metrics in one species, it is no guarantee that this
assembler will work as well with a different genome. The BCM-HGSC team
produced the top ranking assembly for bird and fish but a much lower-ranked
assembly for snake. Comparisons between the performance of the same assembler
in different species are confounded by the different nature of the input

sequence data that was provided for each species.

Take home message from the paper -

>

**Practical considerations for de novo genome assembly**

Based on the findings of Assemblathon 2, we make a few broad suggestions to
someone looking to perform a de novo assembly of a large eukaryotic genome:

1 Dont trust the results of a single assembly. If possible generate several
assemblies (with different assemblers and/or different assembler parameters).
Some of the best assemblies entered for Assemblathon 2 were the evaluation
assemblies rather than the competition entries.

2 Dont place too much faith in a single metric. It is unlikely that we would
have considered SGA to have produced the highest ranked snake assembly if we
had only considered a single metric.

3 Potentially choose an assembler that excels in the area you are interested
in (e.g. coverage, continuity, or number of error free bases).

4 If you are interested in generating a genome assembly for the purpose of
genic analysis (e.g. training a gene finder, studying codon usage bias,
looking for intron-specific motifs), then it may not be necessary to be
concerned by low N50/NG50 values or by a small assembly size.

5 Assess the levels of heterozygosity in your target genome before you
assemble (or sequence) it and set your expectations accordingly.

As you can imagine, this will not be our last post on the topic. This paper
provides an incredible learning opportunity for anyone interested in
assembling a genome.

One thing to note, Assemblathon is a competition to judge only the quality of
the assembly, but two other metrics matter especially for us, poor researchers
- (i) time to assemble, (ii) cost of computer (RAM). Many assembly-related
commentaries in our blog were written to address those issues. Please check
[Supplementary file 2](http://korflab.ucdavis.edu/Datasets/Assemblathon/Assemb
lathon2/Additional_files/Additional_file_2.pdf) for server information from
various groups.

