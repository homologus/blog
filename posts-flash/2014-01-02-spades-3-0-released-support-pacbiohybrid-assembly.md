---
title: SPAdes 3.0 Released with PacBio Hybrid Assembly Module
tags: []
categories:
- blog
---
We received an email from Anton Korobeynikov of Algorithmic Biology Lab about
the release of SPAdes 3.0. Anton mentioned several months back that they were
working to incorporate PacBio reads in hybrid mode, and now it is official !!
You can download the software from
[here](http://spades.bioinf.spbau.ru/release3.0.0/) and the list of changes
are given below.
<!--more-->

We look forward to reading the manuscript that presents their algorithms.
Anton told us that they are working on it, but if it does not come too soon,
we have to start poking around the code :)

>

SPAdes 3.0.0, 29 December 2013

NEW: Module for assemblying diplod highly polymorphic genomes.

NEW: Support for PacBio reads.

NEW: Support for IonTorrent reads.

NEW: Support for Sanger reads and additional contigs.

NEW: Possibility to restart SPAdes starting from the specified check-point
with the --restart-from option.

NEW: Output contigs/scaffolds in FASTA and FASTG.

CHANGE: Improved algorithm for mate-pair repeat resolution and scaffolding.

CHANGE: Improved N50 and misassembly rate for single-cell data sets with low
genome fraction.

FIX: User-friendly handling for errors in mismatch corrector.

REMOVE: Rectangle graph repeat resolution module.

