---
title: CEGMA - a pipeline to accurately annotate core genes in eukaryotic genomes
tags: []
categories:
- blog
---
Instead of relying solely on N50 or other simple measures, Assemblathon-2
paper came up with many novel ways to judge qualities of genome assembly and
one of them is CEGMA. CEG here stands for 'core eukaryotic genes' and
represents a set of 458 highly conserved genes present in all eukaryotes.
<!--more-->

The [original CEGMA paper was published in
2007](http://bioinformatics.oxfordjournals.org/content/23/9/1061.full), but
its importance has only gone up in recent years given that so many highly
complex genomes are being assembled from NGS libraries.

> In this article, we introduce a computational method to obtain a set of
reliable gene structures in any eukaryotic genome. Our goal is not to provide
the complete catalog of genes in a genome, but to generate a highly accurate
set of genes for those genomes without experimental data. The strategy relies
on a simple fact: some highly conserved proteins are encoded in essentially
all eukaryotic genomes. We use the KOGs database to build a set of these
highly conserved, ubiquitous proteins. We call these protein families core
proteins and the genes that encode them core genes. We define a set of 458
core proteins and present an accurate mapping protocol that maps the likely
ortholog of each gene in a genomic sequence and then predicts the exonintron
structure. We show that our procedure does not need any previous knowledge of
the target genome, that it is highly accurate, and that it can be used even
for those genomes in draft stages.

