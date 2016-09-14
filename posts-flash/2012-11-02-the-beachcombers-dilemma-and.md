---
title: 'The Beachcomber''s Dilemma and Diginorm Manual '
tags: []
categories:
- blog
---
![](http://www.homolog.us/blogs/wp-
content/uploads/2012/11/Beaches_Dunes-04-300x198.jpg)
<!--more-->

Even though [Warren Dunes
beach](http://www.epa.gov/ecopage/photo/beaches/Beaches_Dunes-04.html) has no
shell, A [beach-goer from Michigan](http://ivory.idyll.org/blog/beachcombers-
dilemma.html) came up with an interesting dilemma.

>

A beachcomber is interested in obtaining up to 10 examples of every type of
shell present on a beach. The shells are individually easy to find, but some
types are really rare and some are really abundant. The beachcomber has access
to a large group of helpers, and wants to know how to most efficiently divide
up the helpers across the beach to gather the shells most quickly, while
minimizing discussion and communication between the helpers.

Or, more generally, given a data set D containing some unknown number of item
types M with an unknown abundance distribution, how can we most efficiently
recover at least N items of each type from D using Z workers, in the absence
of fast communication between the workers?

There is a fairly easy I/O bound streaming online solution for this, I think,
but I'm interested in knowing if this is isomorphic to an established
algorithms problem.

Please respond in [Titus Brown's blog](http://ivory.idyll.org/blog
/beachcombers-dilemma.html), if you have an algorithm. While going through
comments, we came across [an interesting review
article](http://www.cs.rpi.edu/~zaki/PaperDir/PS/concurrency.pdf) that readers
may find helpful.

> **Parallel and Distributed Association Mining: A Survey**

Mohammed J. Zaki, Rensselaer Polytechnic Institute

The author surveys the state of the art in parallel and distributed
association-rule-mining algorithms and uncovers the fields challenges and open
research problems. This survey can serve as a reference for both researchers
and practitioners.

C. Titus Brown also [posted a detailed manual](http://ivory.idyll.org/blog/an-
assembly-handbook-for-khmer.html) on how to use digital normalization for
various types of data (genome, metagenome, transcriptome, etc.). Looks like we
need to create a new category for diginorm.

