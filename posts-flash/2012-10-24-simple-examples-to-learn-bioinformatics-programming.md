---
title: Simple Examples to Learn Bioinformatics Programming
tags: []
categories:
- blog
---
C. Titus Brown asked in his blog - [What's the equivalent of prime number
calculations for biologists learning to program?](http://ivory.idyll.org/blog
/prime-numbers-for-biologists.html). New students of bioinformatics should
check his commentary and responses to find interesting ideas.
<!--more-->

If we had to design a course on programming for biologists, it will have the
following progression.

**'Hello world'**

It will start with GC-counting of a genome as 'Hello World' example.

**Warm up questions**

b) Early sessions will have the following examples -

i) Writing code to extract nucleotides 12000-14500 on chromosome 3 from human
genome,

ii) Finding reverse complement of a sequence,

iii) Translating a nucleotide sequence in six frames and finding longest
peptide,

**'Prime number'**

Counting k-mers in sequences is equivalent to identifying all prime numbers up
to 10 million in C-programming. Why do we say so? Anyone can write a lousy
program for k-mer counting or prime number counting that does not scale well.
So, both examples are good for teaching the differences between O(N), O(N
logN), O(N^2) types of algorithms.

For the above reason, when we first wrote about Hadoop, we used [the k-mer
counting example](http://www.homolog.us/blogs/2011/08/31/using-hadoop-for-
transcriptomics-an-example-to-get-started/).
[Here](http://www.homolog.us/blogs/2012/03/28/efficient-methods-for-
counting-k-mers/) we described other efficient methods for counting k-mers.
The good thing about k-mer counting is that the problem itself is so easy to
state that it can be used to explain aspects of hardware, memory and hashing.

**'search/sort algorithms'**

In our first course of programming in computer science classes, we started
with simple sort algorithms like bubble-sort, quick-sort, etc.

For bioinformaticians, the equivalent topics are Smith-Waterman alignment and
various other alignment programs.

**'graph algorithms'**

After mastering search and sort, we learned few graph-algorithms. If you read
our blog for the last few months, you know [what the bioinformatics equivalent
would be](http://www.homolog.us/blogs/2011/07/28/de-bruijn-graphs-i/).

**Use of bio** libraries**

We will bring the bioperl, biopython, etc. libraries at the end. Only after
someone appreciates how time-consuming it is to write code for simple-sounding
tasks (finding every match from a BLAST output), it is good to learn that
others already solved the problems.

\-------------------------------

Question for readers:

If you want to estimate GC in a 300 million nucleotide genome and computing is
so expensive that checking each nucleotide costs $3, what is the most logical
solution?

