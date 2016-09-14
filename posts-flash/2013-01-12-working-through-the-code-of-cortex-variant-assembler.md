---
title: Working Through the Code of Cortex Variant Assembler
tags: []
categories:
- blog
---
Yesterday we posted on [Cortex variant
assembler](http://www.homolog.us/blogs/2013/01/11/high-throughput-microbial-
population-genomics-using-the-cortex-variation-assembler/), and had few email
exchanges with Zamin, its author, on a problem we were trying to solve. To
make those exchanges productive, we figured it would be useful to parse the
code and understand the algorithm. That way, we may solve our problem by
slightly modifying his algorithm or by combining his method with
[SPAdes](http://www.homolog.us/blogs/2012/10/19/going-through-the-spades-code-
rectangular-graph/).
<!--more-->

Here are the [wiki pages](http://homolog.us/wiki1/index.php?title=Cortex) for
Cortex. We will briefly explain, what we learned so far. Do not expect too
much from this commentary except some top-level view of the pieces.

Source code for cortex_var is divided into five folder - 'basic',
'count_kmers', 'hash_table', 'cortex_var' and 'test'.

**basic** \- Contains functions to define binary kmers, nucleotide (ATGC) and ABI SOLiD data, etc. They are well written. 

**hash_table** \- Contains functions to describe hash function and hash tables. He uses two types of hash functions - crc (also used by SOAPdenovo2) and Bob Jenkins. Two types of hash tables were created - chain hash and open hash. This part should be easy to follow for anyone, who took a CS class in hashing. 

**count_kmers** \- Kmer counting routines. These routines probably do not get used any more. 

**test** \- test codes. 

**cortex_var** \- This is where real action takes place. We do not understand everything here well, but here is the top level view. 

The directory is divided into 'core' and 'many_colours' subdirectories. The
'main' function is in many_colours/cortex_var.c file. To understand the code,
you can focus on the following five files first. We created wiki pages for
each one listing all its functions.

[cortex_var/core/dB_graph_population.c](http://homolog.us/wiki1/index.php?titl
e=Cortex:cortex_var:core:dB_graph_population.c)

[cortex_var/core/db_complex_genotyping.c](http://homolog.us/wiki1/index.php?ti
tle=Cortex:cortex_var:core:db_complex_genotyping.c)

[cortex_var/many_colours/element.c](http://homolog.us/wiki1/index.php?title=Co
rtex:cortex_var:many_colours:element.c)

[cortex_var/many_colours/genotyping_element.c](http://homolog.us/wiki1/index.p
hp?title=Cortex:cortex_var:many_colours:genotyping_element.c)

cortex_var/many_colours/cortex_var.c - contains 'main'.

The file 'dB_graph_population.c' is the largest (10000 lines) and has
functions with names as
'db_graph_get_perfect_path_for_specific_person_or_pop'. What the functions do
should be self apparent from their names, but we have not had time to think
through the names of 113 or so functions. One difficulty we have is that the
'main' function itself is some 900 lines long. Zamin was kind enough to
explain the logic, and we added [the information in the
wiki](http://homolog.us/wiki1/index.php?title=Cortex).

We will get back to this topic after completing our analysis of SOAPdenovo2.

