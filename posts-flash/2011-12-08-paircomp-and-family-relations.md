---
title: Paircomp - Comparing Two Genomes to Find Conserved cis-regulatory Segments
tags: []
categories:
- blog
---
With sequencing prices falling rapidly, it has now become possible to sequence
the genomes and transcriptomes of multiple related species. This allows
biologists to compare genome sequences of different related species, and find
regions conserved over large evolutionary distance. We came across a really
cool software tool for comparing genomes (paircomp) developed by Eric
Davidson's group in Caltech.
<!--more-->

This program takes two sequences (supposedly regions around the same gene from
two species) and generates plots like these -

![](http://www.homolog.us/blogs/wp-content/uploads/2011/12/Capture-
263x300.png)

In the above figure, two axes show genomic coordinates from two organism. The
program takes a k-mer value as input (let's say 21), and compares all 21-mers
from one sequence with all 21-mers from the other. If the 21-mers match, the
program places a red dot in the graph at the corresponding location. 'Match'
here can be perfect match, or the user can allow to have some mismatch between
the k-mers being compared.

You can also present the same information as the above dot-plot in genomic
view:

![](http://www.homolog.us/blogs/wp-
content/uploads/2011/12/Capture21-263x300.png)

Two sequences being compared are shown at the top and bottom. A thin line
connecting them matching 21-mers between two sequence. When many such lines
fall next to each other, you see a thick line representing a conserved patch.

You can download the latest version of paircomp from
[here](https://github.com/ctb/paircomp). Installation is straightforward,
provided you have the latest version of python installed. Older versions are
available [here](http://family.caltech.edu/) along with papers, manuals and
the viewer program.

Paircomp is a combination of three modules -

i) A C++ program (paircomp) that compares two sequences and generates a table
with many lines (each representing a red dot), each having four columns -
coordinate in sequence 1, coordinate in sequence 2, number of matching
nucleotides and strand. The program is run as 'paircomp seq1 seq2 K-mer-size
threshold output-file'. Threshold=.8 means any match over 80% similarity will
be reported.

ii) A simple python program that converts the above paircomp output into a XML
file. This python program adds the sequences and gene annotations if any to
the paircomp output.

iii) A viewer program (FamilyRelations) to view the above XML output. The
images we showed above are from the viewer program.

