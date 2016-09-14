---
title: 'SplitMEM: Graphical Pan-genome Analysis with Suffix Skips'
tags: []
categories:
- blog
---
Sidenote - For [those of you asking questions on
Contrail](http://www.homolog.us/blogs/blog/2011/09/08/contrail-a-de-bruijn-
genome-assembler-that-uses-hadoop/), we asked M. Schatz in twitter.
<!--more-->

![Capture](http://www.homolog.us/blogs/wp-
content/uploads/2014/04/Capture5-300x194.png)

\---------------------------------------------------------

Michael Schatz [posted a new preprint in
arxiv](http://www.biorxiv.org/content/early/2014/04/06/003954). We have not
read it yet, but the abstract appears promising. We will get back to it later,
but for readers' benefit here is what it is all about.

>

Motivation: With the rise of improved sequencing technologies, genomics is
expanding from a single reference per species paradigm into a more
comprehensive pan-genome approach with multiple individuals represented and
analyzed together. One of the most sophisticated data structures for
representing an entire population of genomes is a compressed de Bruijn graph.
The graph structure can robustly represent simple SNPs to complex structural
variations far beyond what can be done from linear sequences alone. As such
there is a strong need to develop algorithms that can efficiently construct
and analyze these graphs.

Results: In this paper we explore the deep topological relationships between
the suffix tree and the compressed de Bruijn graph. We introduce a novel O(n
log n) time and space algorithm called splitMEM, that directly constructs the
compressed de Bruijn graph for a pan-genome of total length n. To achieve this
time complexity, we augment the suffix tree with suffix skips, a new construct
that allows us to traverse several suffix links in constant time, and use them
to efficiently decompose maximal exact matches (MEMs) into the graph nodes. We
demonstrate the utility of splitMEM by analyzing the pan- genomes of 9 strains
of Bacillus anthracis and 9 strains of Escherichia coli to reveal the
properties of their core genomes. Availability: The source code and
documentation are available open- source at http://splitmem.sourceforge.net

For other related methods, readers are encouraged to check -

[Compressed Full-Text Indexes for Highly Repetitive Collections (Jouni
Sirn)](http://www.homolog.us/blogs/blog/2013/09/04/compressed-full-text-
indexes-highly-repetitive-collections-jouni-siren/)

[Compressed Spaced Suffix Arrays](http://www.homolog.us/blogs/blog/2013/12/13
/compressed-spaced-suffix-arrays/)

[HAL: a Hierarchical Format for Storing and Analyzing Multiple Genome
Alignments](http://www.homolog.us/blogs/blog/2013/05/22/hal-a-hierarchical-
format-for-storing-and-analyzing-multiple-genome-alignments/)

[Sibelia, a dBG-based Tool to Find Synteny in Multiple Closely Related
Microbes](http://www.homolog.us/blogs/blog/2013/08/02/sibelia-a-dbg-based-
tool-to-find-synteny-in-multiple-closely-related-microbes/)

[SiBELia/SyntenyFinder A de Bruijn Graph-based Tool for Finding
Syntenies](http://www.homolog.us/blogs/blog/2012/10/17/sibeliasyntenyfinder-a
-de-bruijn-graph-based-tool-for-finding-syntenies/)

Thanks to Ilia Minkin, the first author of Sibelia, for pointing out his
relevant paper. The readers may find following comments useful in comparing
Sibelia with splitMEM. Edit. He also wrote a blog-post on this topic and it is
available [here](http://minkinpark.blogspot.ru/2014/04/on-direct-construction-
of-de-bruijn.html).

![Capture](http://www.homolog.us/blogs/wp-
content/uploads/2014/04/Capture6-300x49.png)

![Capture2](http://www.homolog.us/blogs/wp-
content/uploads/2014/04/Capture22-300x216.png)

