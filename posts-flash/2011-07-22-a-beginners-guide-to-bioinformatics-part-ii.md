---
title: A beginner's guide to bioinformatics - part II
tags:
- introductory
- bioinformatics
categories:
- blog
---
In [part I](http://www.homolog.us/blogs/?p=85), I described Layers 1-3 of
learning bioinformatics for solving biological problems. Let me cover two
expert levels here.
<!--more-->

**Layer 4 - High level coding in C/C++, Java for implementing existing algorithms or modifying existing codes for new functionality**

Those who try to be on the cutting edge of solving biological problems often
reach the limits of layers 1-3 very quickly. This is even more important these
days, because biology is getting very data intensive. Let me give few examples
-

i) Let's say a lab invested money for an ABI SOLiD sequencing machine, but a
new paper on aligning sequences came out that does not cover SOLiD color-space
data yet. Should the lab throw away its sequencing instrument and buy
something new?

ii) As another example, let's say a lab has arrangements with a high-end
computing center to use 100 parallel processors, but the best assembly program
he found only runs on single machine that requires 512 Gb of RAM. Should the
lab buy another new RAM-heavy computer ($50-100K) ?

iii) A supposedly very accurate algorithm was described in a journal, but the
authors only provided assembled code and not source code for their method. You
have a different data type (let's say SOLiD data or shorter read lengths than
the algorithm described). What should you do?

Various questions of above type come up almost every day, and modifying
existing software codes is the best way to address them. This layer requires
expertise in one or more high level programming languages such as C, C++ and
Java, and ability to understand algorithms described in the journal. It is
absolutely necessary, if a a lab or core facility wants to fully utilize its
capabilities. By restricting itself only to readily developed programs, the
lab is unable to fully utilize the capabilities of its expensive instruments.

**Layer 5 - Thinking mathematically, developing own algorithms and implementing in C/C++/Java codes**

A new efficient algorithm gets used millions or billions of times over many
years by labs all around the world. BLAST is one good example. To provide some
recent examples on next-gen sequencing, alignment programs such as Bowtie and
BWA used Burrows-Wheeler transform, a mathematical transform, to dramatically
increase speed of aligning many short sequences on a reference genome. Next-
gen assembly programs such as Velvet or SOAPdenovo use de Bruijin graphs, a
graph-theoretic technique, and can allow assembly of large genomes for a
fraction of costs of even five years back.

Developing these programs require mathematical brain, which is far from
biology. One of my motivations for this blog is to explain some of these
algorithms in simple languages so that those intrepid souls, who like to
experiment on new codes, can try them out easily.

