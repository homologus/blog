---
title: De novo Assembly is not at all Black Art
tags: []
categories:
- blog
---
![Capture](http://www.homolog.us/blogs/wp-
content/uploads/2013/06/Capture2-300x64.png)
<!--more-->

We are puzzled to read the above comment. Over the last few months, we
exchanged emails with a number of authors of various NGS genome assembly
programs and none appeared like a black artist. Our only suspicion is that
Jared Simpson, the author of two major assembly programs, is a sophisticated
computer program, because no matter at what hour we ask him an assembly-
related question, we get a detailed answer within few seconds. Even Google
algorithm is not that fast !!

Jokes aside, genome assembly is no more black art than short read alignment,
clustering or any other bioinformatics tasks. The best way to gain insight
into the process is to think about a well-assembled genome (the final product)
and follow the steps backward. Ruiquiang Li of BGI did that in [their 2010
Genome Research paper](http://genome.cshlp.org/content/early/2009/12/16/gr.097
261.109.full.pdf+html) \-

>

The main difficulty of assembling a shotgun short read data set into

a complete genome is the presence of repetitive sequences that have multiple
identical or very similar copies in the genome. Thus, analyzing the repeat
structure of a known reference genome or closely related species would help
for designing the sequencing project and provide a theoretical estimation of
the expected assembly.

In humans, about half of the genome is derived from transposable elements
(TEs) (Lander et al. 2001). Most transposons are under neutral selection, so
new copies will accumulate mutations quickly after duplication and will become
easily distinguishable from the other repeat copies. On analyzing the human
genome, we found that ~79% of the sequence was composed of unique 25-mers.
Length distribution of the continuous repetitive 25-mers showed that over 47%
of the repeat clusters are shorter than 1 kb (Fig. 1A). There are two peaks
with repeat-cluster lengths of about 300 bp and 6 kb, which correspond to the
two most abundant TE classes in the human genome: Alu and L1 retrotransposons,
respectively. Over 78% of the unique clusters range between 500 bp and 5 kb.
So, theoretically, at an appropriate sequencing depth, using a 25-mer as the
node size for assembly, the expected contig N50 size of the unique sequences
will be 1.3 kb; reducing seed size to a 21-mer, the expected contig N50 size
would be as short as 251 bp; and increasing it to a 29-mer gives an expected
contig N50 of 1.9 kb (Supplemental Fig. 1). Bigger K-mers would give longer
contig sizes, but would require deeper sequencing or longer read length to
guarantee that short reads overlap more than a selectedK-mer size at each
genomic location.

Resolving the repeat clusters between unique clusters and assembling them into
an intact sequence requires the paired-end relationship of a pair of short
reads generated from both ends of a DNA clone. If both of the two reads are
unique and located on two neighboring unique clusters, then we can order these
two unique clusters, estimate the distance according to the clone insert size,
fill in the internal repeat cluster, and join them into a long sequence. Thus,
in principle, a repeat cluster of size N could be crossed by paired-ends with
a clone insert size longer thanN. Using 200, 500, 2000, 5000, and 10,000 bp
insert size of paired-ends, the expected scaffold N50 size of the human genome
is 4, 18, 158, 562, and 9870 kb, respectively (Fig. 1B). Of course, to fill in
the intrascaffold gaps effectively, and avoid interleaving, stepwise pairedend
insert sizes would be needed.

Think about what is going on here. All genomes are made up of [unique regions
and repeatitive regions](http://homolog.us/Tutorials/index.php?p=3.2&s=1), and
the unique regions are quite easy to reconstruct in an assembly process. There
is no conceptual difficulty there, and all programs more or less agree about
the output. Then the programs arrange those unique regions within their
genomic context using mate pairs, and that process is not complicated either.

What makes genome assembly process feel like black art is our expectation that
'genome assembly' programs would spit out long and perfect chromosomes. That
may be impossible from the data and may complicate matters in other cases.
However, the programs try to give long scaffolds, because we expect them to do
so and evaluate programs based on simple and meaningless measures like N50. If
the users of assembly program reject N50 and try to think about the process,
genome assembly will not appear like black art any more. We tried our best to
explain de Bruijn graphs in [these
tutorials](http://homolog.us/Tutorials/index.php?p=1.1&s=1), and will upload
another set on genome assembly, when time permits.

