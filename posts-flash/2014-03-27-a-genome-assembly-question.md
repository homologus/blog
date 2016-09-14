---
title: A Plant Genome Assembly Question
tags: []
categories:
- blog
---
We came across [the following
question](http://seqanswers.com/forums/showthread.php?t=41961) in seqanswers -
<!--more-->

>

Hi All!

My name is John Henning and I'm working with the organism Humulus lupulus L--
commonly known as "hops." I work for USDA-ARS and am housed at Oregon State
University.

I'm currently working on sequencing the hop genome and have been using velvet
for the first round of de novo sequencing. Have had a few runs that have
successfully completed but not happy with the results (N50 = 270 - 1000).
Thus, I've come here seeking answers from you experts!!

For readers' benefit, we list here the steps we would take to solve a similar
problem.

1\. **Biological question**

We usually start with the biological question being answered through genome
assembly, because the time and effort invested in a large genome assembly is
wasted, if the planning about addressing the biological question is not
properly done. Some plant genomes are too big and assembling them to high
quality could be expensive. Often transcriptomes are enough to start answering
the biological question. In other examples, the right tissue or the right
species is not chosen, and therefore the genome assembly needs to be followed
by another genome assembly sooner or later. Polyploidy is big issue for plant
genomes.

A bit about p[hylogenic position and relevance of H.
lupulus](http://en.wikipedia.org/wiki/Cannabaceae) \-

> Cannabaceae is a small family of flowering plants. As now circumscribed, the
family includes about 170 species grouped in about 11 genera, including
Cannabis (hemp), Humulus (hops) and Celtis (hackberries). Celtis is by far the
largest genus, containing about 100 species.[1]

Other than a shared evolutionary origin (see Phylogeny below), members of the
family have few common characteristics; some are trees (e.g. Celtis), others
are herbaceous plants (e.g. Cannabis).

2\. **Relevant published genomes**

Next we look into what the closest published genome is. After completing
genome assembly, the researchers need to do genome annotation and comparative
analysis to figure out anything. Sometimes, having a closely related genome
helps in scaffolding step - which is very painful and error-prone for large
assemblies.

[Here
](http://genomevolution.org/wiki/index.php/Sequenced_plant_genomes#Cannabis)is
a list of all sequenced plant genomes. Relevant information about the
requested plant is given below.

> Cannabis

The genome of cannabis (Cannabis sativa) was published in Genome Biology in
October 2011. The genome sequence was completed using a mixture 454 and
Illumina sequencing, with mate pairs used to bridge gaps in the assembled
regions. As a result, while only 534 megabases of the genome were assembled
the genome spans >786 Mb of sequence (the extra 200 MB are NNNNNN's
representing unassembled repeat sequences -- transposons -- of known length
between sequenced regions of the genome). In addition to the genome itself,
the same research group generated a great deal of tissue specific RNA-seq data
from multiple cannabis cultivars.

Genome Paper: Harm van Bakel et al "The draft genome and transcriptome of
Cannabis sativa." Genome Biology DOI: 10.1186/gb-2011-12-10-r102

3\. **Sequencing**

Now that we know about the biological question and related genomes, it is
important to decide about sequencing library mix carefully. What mate-pair
lengths are chosen? Do we include some Illumina and some PacBio reads? How
many libraries of each combination is being sequenced? Do we have enough
coverage?

4\. **Assembly**

Velvet is not a good program for assembling large genomes and nobody uses it
for that purpose. We usually follow this procedure -

(i) Use dsk or jellyfish to understand the k-mer characteristics of the reads.

If the coverage is not deep with the available reads, then the remaining steps
will not work and the assembly will be poor. Also, checking for k-mer
distribution gives one some impression about repeat content,

(ii) Use SOAPdenovo2 to generate the first draft

We have found SOAPdenovo2 to be the most efficient program for this purpose.
All programs (SOAPdenovo2, ALLPATHS) make some errors in automated mode, but
ALLPATHS makes those errors over 1TB RAM and one months, whereas SOAPdenovo2
does the same over 1/20th of time and resources.

(iii) Use Minia at multiple k-mer values to get the contigs right

We wrote several commentaries to explain how de Bruijn graph based genome
assemblers work (see
[here](http://www.homolog.us/Tutorials/index.php?p=1.1&s=1)). The contig
assembly step is gap free and fewer errors we have there, more accurate the
following steps would be. We have found Minia to be very accurate in this
task.

(iv) Compare SOAPdenovo2 assembly with Minia to check for corrected contiguity

Now that we have the Minia contigs, we use them to fix any local errors in the
SOAPdenovo2 assembly. That takes care of any shortcomings in (ii).

(v) Use Pacbio reads and information from (iv) to redo scaffolding

(vi) If a related genome is available, use it for scaffolding as well.

\------------------------------------------------------------------

After step (v - vi), one should have a reasonable assembly and whether to
improve it further depends on how the biological questions are being
addressed. Genome assembly is an endless process, if you really want to get
the chromosomes complete and right. Even the human genome is not 'complete'
yet.

At this stage, we can have two options -

(i) the scaffolds are too sparse and more reads are needed (bad news - back to
3, but it is important to understand why)

(ii) the genome is good enough to proceed with annotation and other work (good
news)

\-------------------------------------------------------------------

Edit.

**One last point**

We try to focus on the biological problem and then combine genome assembly,
RNAseq assembly and whatever else to get to the answer as soon and as
inexpensively as possible. This is quite different from what others would
advocate. In the traditional approach, the genome assembly and annotation
takes about two years and then another year to get the paper published. By
then, you are exhausted and have not contributed anything to answer the unique
biological questions about the species.

In a 2008 interview, [Sydney Brenner said](https://www.dropbox.com/s/3pmx20oi1
aq6elu/intervew%20sydeny%20brenner%202008.pdf) (h/t: @dangraur) -

> **How has molecular biology research changed in the past 50 years?**

It has changed completely. It has become much more descriptive and much less
experimental. It is what I call low input, high throughput, no output science!
The

proponents of this kind of science claim that by generating descriptions of
the behaviour of biological systems theyll be able to generate models of whats
going on in them, and then refine these models. They call this systems
biology. To use a simple analogy of this type of science, consider that one is
sitting outside a room in which someone is playing a drum. The room is wired
for sound, and using only the recording of the sounds one is trying to
reconstitute the physical properties of the drum. In my mind one cannot
succeed because in this classic inverse problem, information is lost and
measurements are inaccurate. The best thing to do is to tackle the problem
directly by studying the drum then one can play it oneself. That is what
molecular biology is about. It is mechanism based and causation based. But
nowadays scientists arent asking as many mechanistic and causative questions.

In our approach, we try to figure out how we can get to the drum fast.

