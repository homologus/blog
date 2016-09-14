---
title: 'MEDUSA: a Multi-draft Based Scaffolder'
tags: []
categories:
- blog
---
[Link](http://bioinformatics.oxfordjournals.org/content/early/2015/03/24/bioin
formatics.btv171.short)
<!--more-->

> Motivation: Completing the genome sequence of an organism is an important
task in comparative, functional and structural genomics. However, this remains
a challenging issue from both a computational and an experimental viewpoint.
Genome scaffolding (i.e. the process of ordering and orientating contigs) of
de novo assemblies usually represents the first step in most genome finishing
pipelines.

Results: In this paper, we present MEDUSA (Multi-Draft based Scaffolder), an
algorithm for genome scaffolding. MEDUSA exploits information obtained from a
set of (draft or closed) genomes from related organisms to determine the
correct order and orientation of the contigs. MEDUSA formalises the
scaffolding problem by means of a combinatorial optimisation formulation on
graphs and implements an efficient constant factor approximation algorithm to
solve it. In contrast to currently used scaffolders, it does not require
either prior knowledge on the microrganisms dataset under analysis (e.g. their
phylogenetic relationships) or the availability of paired end read libraries.
This makes usability and running time two additional important features of our
method. Moreover, benchmarks and tests on real bacterial datasets showed that
MEDUSA is highly accurate and, in most cases, outperforms traditional
scaffolders. The possibility to use MEDUSA on eukaryotic datasets has also
been evaluated, leading to interesting results.

Availability: MEDUSA web server: http://combo.dbe.unifi.it/medusa A stand-
alone version of the software can be downloaded from
https://github.com/combogenomics/medusa/releases. All results presented in
this work have been obtained with MEDUSA v. 1.3.

Contact: marco.fondi@unifi.it

