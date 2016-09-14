---
title: Part 3 - GC Distribution of Genomes (Casual)
categories:
- ncRNA
---
Instead of beating around the bush, we would like to dig into genomic data
starting from this commentary. Today's discussion will present several core
concepts that will act as basic building blocks for our future commentaries.
We plan to do it in the following manner. This presentation will be made in
simple language making no assumption about the technical background of the
reader. The next commentary will discuss the same information in a more formal
tone citing past work from other researchers. Interesting original results
will be presented in subsequent commentaries.
<!--more-->

In our work, we investigated nucleotide distributions in various genomes and
observed unusual patterns among a set of important genes. Nucleotide
distribution is the most visible, yet least discussed, aspect of a genome.
When you download a new genome, a large FASTA file with many letters As, Cs,
Gs and Ts appear in your computer. If the file contained hieroglyphic text or
secret spy code, you would have started with counting letters, duplets
(dinucleotides), triplets, etc. to see if any odd pattern emerged from them.
The geneticists do not consider the genome as a secret spy code, because they
already know that it contains genes and 'junk DNA'. Therefore, the members of
various genome projects usually jump straight to finding genes of interest
rather than wasting time looking for other hidden patterns. We note that the
region previously known as 'junk DNA' is now considered valuable with
information on [cis-regulatory controls](http://sugp.caltech.edu/endomes/).

In an unconventional line of genome-centric investigation, David Haussler's
group [found the presence of 481 segments longer than 200 bp that are
absolutely conserved between orthologous regions of the human, rat, and mouse 
genomes](http://www.stanford.edu/class/cs273a/papers.spr07/lecture7/Bejerano20
04.pdf). Other such patterns may emerge, if the genomes are investigated from
scratch as 'secret spy codes', but such investigations are not part of
mainstream genome analysis. A typical genome paper covers the topic of
nucleotide distribution very briefly and then moves on to issues related to
genes. [Here is an example from a recent paper:](http://www.plosbiology.org/ar
ticle/info%3Adoi%2F10.1371%2Fjournal.pbio.1000313)

> The assembled regions of the pea aphid genome have the lowest GC content of
any insect genome sequenced to date; at 29.6%, pea aphid GC content is 5.2%
lower than that of Apis mellifera at 34.8% [40]. Computed over all
concatenated transcripts pea aphid GC content averages 38.8% (SD = 8.4, N =
37,994), a value similar to that of Apis mellifera (mean = 38.6%, SD = 9.7, N
= 17,182) (Table S2).

In the remaining discussion, we shall introduce three terms that will be used
in our future discussions. There is nothing complicated about them, but we
thought it would be helpful to define them here to help our readers.

**A. GC content**

The simplest number one can compute for a new genome is its overall GC
content. It is calculated by taking the ratio of total number of [G/C]
nucleotides and the genome size. _Plasmodium falciparum_, a mosquito parasite
has the lowest GC content (20%) among all eukaryotes. Typical GC contents for
various sequenced genomes are shown below.

Yeast (Saccharomyces cerevisiae)

38%

Fruit fly (Drosophila menalogaster)

43%

Arabidopsis thaliana

36%

Human

41%

Mouse

42%

Here we list GC contents for few insect genomes.

Fruitfly (Drosophila)

43%

Honeybee (Apis melifera)

34.8%

Beetle (Tribolium)

34%

Wasp (Nasonia)

41.7%

Pea aphid

29.6%

**B. GC distribution**

GC content is a single number to describe an entire genome. That number makes
sense for small genomes, because the variability around the genome is low. For
large genomes, local GC content varies greatly in different regions, and one
number does not do justice for the entire genome.

We perform a simple calculation to estimate variability in a genome, where we
cut 1Kb blocks from different randomly selected (uniform distribution) regions
the genome, and measure their GC contents. The median of those numbers is
close to GC content of the genome, but we also plot the distribution. If the
distribution is tight (low standard deviation), that suggests that the genome
has uniform GC content. If the distribution is not tight (high standard
deviation), that means GC-content varies greatly around the genome.

**C. Isochores**

Genomes with widely varying GC content can be partitioned into sub-regions
with nearly uniform GC content. Those sub-regions are called isochores.

**D. GC content of Third codon - GC3**

GC content of protein-coding genes is another easy-to-compute, yet
informative, number to describe nucleotide distribution of a genome. Each
codon of genetic code consists of three nucleotides, among which the third
nucleotide can vary greatly without changing the translated peptide sequence.
Here is an example -

![](http://www.homolog.us/blogs/ncrna/wp-content/uploads/sites/3/2012/03/GC-
paper-300x122.png)

GC3 is the GC-content of third bases of codons. In the above example, third
bases for CDS1 and CDS2 are GAAAAGAAAAA and GGCGGGCGCCA. Therefore, GC3 for
CDS1 is AT-rich and GC3 for CDS2 is GC-rich, even though both sequences
translate into the same protein. Typically GC3 matches the GC distribution of
the genomic region (isochore), where the gene is located.

Next post **Part 4 - GC Distributions of Genomes (Formal)**

