---
title: Patterns of Three
tags: []
categories:
- blog
---
> There Are Two Kinds of People In The World: Those Who Think There Are Two
Kinds of People In The World and Those Who Dont.
<!--more-->

Ever since we heard the above quote, we started noticing patterns of threes in
the world :)

\-------------------

There are three ways to deal with NGS data analysis. The most common way is to
download published programs (assemblers, aligners, etc.) , learn about its
parameters and command line options, and run them on your data set. Second way
is to understand the inner working of the programs and adjust your data to
optimize the run. Third way is to start from algorithms instead of programs,
write your own code and analyze the data.

Most people use the first method, because it is the only way to process many
different data sets in a 'core facility' mode. An example of second way is
[digital normalization approach developed by Titus Brown's
group](http://www.homolog.us/blogs/2012/04/02/digital-normalization-from-c
-titus-brown/). In this method, one typically uses Velvet or other commonly
used assemblers, but libraries are reduced in size to remove redundancy. The
third method ([writing an assembler like
SPAdes](http://www.homolog.us/blogs/2012/10/25/rectangular-graph-algorithm/))
is considered 'reinventing the wheel' by some and 'bread and butter' by
others. Surely it is the best way to get the most out of data, and in some
cases the only way to solve challenging problems (such as single-cell assembly
addressed by SPAdes).

\------------------

If you follow the third way above, there are three steps in writing a good
program. The first step is to implement the algorithm in a scripting language
like PERL/python and make it work on a very small data set. In this step, you
are essentially making sure that your implementation of algorithm works, and
do not care about efficiency gained through optimal use of hardware.

In the second step, the same program is ported in C/C++ by using data
structures from standard libraries. At the end of this step, you have the
exact replica of your program in the low level language of your choice.

In the third step, we go through every function and data structure of the
above program and try to make sure they are optimally designed. It is very
difficult work and needs good understanding of underlying hardware (
(processors, memory, cache structure, hard drive, etc.). In the following
post, we will present an excellent example from stackoverflow that can be used
for bioinformatics.

One advantage of using three steps mentioned above is that even if you cannot
optimize all stages of the program, you can be sure it works. The worst
program is the one that does not run at all.

\-------------------

There are three ways to let the community know about your discoveries. First
way is to use the old practice to keep sending papers to various journals and
get rejected for minor technicalities. Second was is to post your preprint in
arxiv.org, discuss results in your blog and argue with journals in parallel.
Third way is to publish your original papers in the blog and send the journals
packing.

\--------------------

There are three ways to do biology these days.

First way - you can continue to do 'one gene at a time' analysis using small-
scale lab work.

Second way - you can scale up the same with large-scale techniques
(microarray, high-throughput sequencing, etc.) and publish one hundred unusual
genes at a time without realizing that [noise also scaled
up](http://www.wired.com/wiredscience/2011/07/longevity-genetics-study-
retracted-from-science/).

Third way is to understand that large-scale experiments are different beasts
and need to be analyzed properly.

\----------------

Finally, there are three ways to deal with US election. The first way is to
[go gaga about Obama and flood social
media](http://www.homolog.us/blogs/2012/10/21/j-craig-venter-and-rise-of-
american-hitler/). Second way to go gaga about Romney and flood unsocial
media. Third way is to laugh at the [sheer idiocy of the entire
process](http://www.youtube.com/watch?v=sZLqsRqKFyI) and pray that it stays
the same to provide [more materials for
laughter](http://www.youtube.com/watch?v=efKguI0NFek) :)

<iframe width="560" height="315" src="http://www.youtube.com/embed/mKQs-jDI7j8" frameborder="0"> </iframe>
