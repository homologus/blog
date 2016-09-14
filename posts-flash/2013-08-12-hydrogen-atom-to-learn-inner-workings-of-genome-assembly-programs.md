---
title: '"Hydrogen Atom" to Learn Inner Workings of Genome Assembly Programs'
tags: []
categories:
- blog
---
Many of the claims in this post are wrong and we just realized that after
reading Anton's comment. We were using the test set that actually came with
SPAdes tar file last year.
<!--more-->

The test set itself is real however, and has proven to be very helpful for
working on assemblers and other bioinformatics programs.

Those, who try to understand various algorithms (say number sorting or graph
traversal), usually play with a small set and try the algorithm 'on paper'
before implementing it as a program. Learning the inner workings of genome
assembly algorithms in that way poses some difficulties, because popular
genome assembly programs spend quite a bit of time taking care of noise in the
data (tip removal, bubble popping, etc.). So, the test data set not only needs
to mimic the genome sequence but also needs to include enough noise to look
like real NGS library. Such a test case is hard to create, and the best
solution is to take an actual NGS library of some species.

SPAdes guys made extensive use of two [E. coli
libraries](http://spades.bioinf.spbau.ru/release2.5.0/manual.html#sec3.3),
which we think are possibly the best realistic test cases. Other researchers
use _B. cereus_ and few other bacterial libraries for testing their programs.
Those data sets are excellent for beta-testing an actual assembler, but may
not be good for 'pencil and paper' analysis of the algorithms.

We created a small 'library' with ~8,000 paired end reads, covering a 1000 nt
region of the the _E. coli_ genome. When we try to assemble with small k-mer
size (11, 13, 15), the reads organize into 706 nt and 218 nt regions, and then
need to be scaffolded. So, the data set provides opportunities to learn about
a number of assembly-related concepts. So far it helped us quite a bit to
figure out the algorithms of various programs. For example, the data set was
immensely helpful, when we worked on the rectangular graph algorithm. It is
from a real measurement and therefore has all the expected 'noise' that you
would expect in an NGS library. We like to integrate it into our tutorials on
genome assembly programs, but if you have a different suggestion, please let
us know. Email us, if you like to use the test data set for a class or other
purpose and we will send you the files (only 200K compressed).

