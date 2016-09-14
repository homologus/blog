---
title: A Simulator for Pacbio Reads
tags: []
categories:
- blog
---
[PBSIM: PacBio reads simulatortoward accurate genome assembly](http://bioinfor
matics.oxfordjournals.org/content/early/2012/11/04/bioinformatics.bts649.short
?rss=1)
<!--more-->

> Our analysis of 13 PacBio datasets showed characteristic features of PacBio
reads (e.g., the read length of PacBio reads follows a log-normal
distribution). We have developed a read simulator, PBSIM, that captures these
features using either a model-based or sampling-based method. Using PBSIM, we
conducted several hybrid error correction and assembly tests for PacBio reads,
suggesting that a CLR coverage depth of at least 15 in combination with a CCS
coverage depth of at least 30 achieved extensive assembly results.

**Availability** \- PBSIM is [freely available from the web](http://code.google.com/p/pbsim/) under the GNU GPL v2 license. 

**Open challenge** \- who can write a simulator for PacBio stock? :) 

\---------

We came across another paper (ht: Jason Chin) that may interest researchers
working on the same topic. This one attempts to derive a statistical model for
nucleotide variation in PacBio data.

> **Modeling kinetic rate variation in third generation DNA sequencing data to
detect putative modifications to DNA bases**

Genome Res. published online October 23, 2012

Eric Schadt, Onureena Banerjee, Gang Fang, et al.

Current generation DNA sequencing instruments are moving closer to seamlessly
sequencing

genomes of entire populations as a routine part of scientific investigation.
However, while

significant inroads have been made identifying small nucleotide variation and
structural

variations in DNA that impact phenotypes of interest, progress has not been as
dramatic

regarding epigenetic changes and base-level damage to DNA, largely due to
technological

limitations in assaying all known and unknown types of modifications at genome
scale. Recently

single molecule real time (SMRT) sequencing has been reported to identify
kinetic variation

(KV) events that have been demonstrated to reflect epigenetic changes of every
known type,

providing a path forward for detecting base modifications as a routine part of
sequencing.

However, to date, no statistical framework has been proposed to enhance the
power to detect

these events while also controlling for false positive events. By modeling
enzyme kinetics in the

neighborhood of an arbitrary location in a genomic region of interest as a
conditional random

field, we provide a statistical framework for incorporating kinetic
information at a test positions

of interest as well as at neighboring sites that help enhance the power to
detect KV events. The

performance of this and related models is explored, with the best performing
model applied to

plasmid DNA isolated from Escherichia coli and mitochondrial DNA isolated from
human brain

tissue. We highlight widespread kinetic variation events, some of which
strongly associate with

known modification events while others represent putative chemically modified
sites of

unknown types.

