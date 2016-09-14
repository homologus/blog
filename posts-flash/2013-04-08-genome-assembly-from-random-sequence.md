---
title: Genome Assembly from Random Sequence
tags: []
categories:
- blog
---
[In our tutorial section](http://www.homolog.us/Tutorials/), we mentioned that
genome assembly problem would not have become a real issue, if genomes were
truly random sequences. Michael Schatz presents a detailed example in the
attached twitter conversation.
<!--more-->

![Capture](http://www.homolog.us/blogs/wp-content/uploads/2013/04/Capture-
286x300.png)

What is the mathematics behind above calculation? If we split a random genome
into k-mers (k=63) and construct a de Bruijn graph, all k-mers are different
due to randomness of the genome. We start getting duplicate k-mers, only when
the genome size reaches the order of 4^63 (=8e37). If k-mers are not repeated
in the genome, de Bruijn graph will be able to assemble the entire genome
without any problem.

Real genomes are far from random and that is where the assembly challenge
lies.

\----------------------------

Edit. That comment about getting duplicates only after genome size was close
to 8e37 was sloppy, as Michael Schatz and Pall Melsted pointed out. We
inserted 'of the order of' with some idea of that sort, but did not work out
the numbers.

![Capture](http://www.homolog.us/blogs/wp-
content/uploads/2013/04/Capture2-300x140.png)

For those unfamiliar with birthday paradox, [here is an old blog
commentary](http://www.homolog.us/blogs/2012/07/30/when-is-your-birthday/).

