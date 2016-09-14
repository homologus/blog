---
title: Modularizing SOAPdenovo2 Code into Four Components
tags: []
categories:
- blog
---
We discussed the code of SOAPdenovo assembler in January and [ended
with](http://www.homolog.us/blogs/blog/2013/01/31/more-soapdenovo2
-commentaries-will-come-in-february/) \-
<!--more-->

> Here is our bigger objective. We plan to split all major assemblers into
code components and mix and match them to assemble the fish library in
Assemblathon 2, which was the hardest to assemble. We like to understand the
results of Assemblathon 2 at the algorithmic level, and explain to our
readers.

In between other work kept us busy, but finally we managed to go through the
SOAPdenovo2 code and split it into four components.

![pic1](http://www.homolog.us/blogs/wp-
content/uploads/2013/08/pic1-300x196.png)

![pic2](http://www.homolog.us/blogs/wp-
content/uploads/2013/08/pic2-300x210.png)

![pic3](http://www.homolog.us/blogs/wp-
content/uploads/2013/08/pic3-300x188.png)

![pic4](http://www.homolog.us/blogs/wp-
content/uploads/2013/08/pic4-300x251.png)

Each component compiles on its own and gives the result of the respective
stage (pregraph, contig, map, scaff). So, if we can generate identical set of
outputs from a different assembler, those files can be fed into the remaining
stages of SOAPdenovo2 to complete the assembly.

The code of SOAPdenovo2 uses [pthreads, not
openMP](http://www.homolog.us/blogs/software/2013/08/04/pthreads-or-openmp/).
That allows finer level of control over the parallel blocks and thus faster
execution. MPI codes, on the other hand, are easier to understand and update.

What can we do with the modules? Here are the possibilities -

i) Replace pregraph stage with [Minia-like Bloom filter
algorithm](http://www.homolog.us/blogs/blog/2012/10/01/minia-assembly-
algorithm-and-french-revolution/) to reduce memory (RAM) requirement,

ii) Try multi-kmer approach, which does not work well with the current
SOAPdenovo2. There is no guarantee that we can do better, but we have some
ideas.

iii) Try [rectangular graph style
algorithm](http://www.homolog.us/blogs/blog/2012/09/12/from-de-bruijn-graphs-
to-rectangle-graphs-for-genome-assembly/) along with the current scaffolder.

iv) Fool the scaffolding unit with PacBio reads to try hybrid assembly.

v) If everything else fails, we can at least make the modified assembler print
a wisecrack every few minutes, while you are waiting for the results. That
will be [The Onion version of a genome
assembler](http://www.theonion.com/articles/scientists-finally-pronounce-
human-genome,33502/) :)

We are trying to figure out a way to post the above code in github without
creating too much confusion with the original version.

