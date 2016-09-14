---
title: NOSQL Databases for Bioinformatics
tags: []
categories:
- blog
---
We presume most readers are not familiar with NOSQL databases. So, we need to
introduce the concept first before delving into their potential benefits for
bioinformaticians.
<!--more-->

Let us consider the problem of deriving [de Bruijn graph of a
genome](http://www.homolog.us/blogs/2011/07/28/de-bruijn-graphs-i/). Suppose
you have a large mammalian genome and you like to build a de Bruijn graph from
the genome sequence. While you were busy working in the lab, [your country
lost access to the credit market](http://www.zerohedge.com/news/friday-dump-
complete-moodys-warns-spanish-downgrade-threatens-aaa-countries-case-grexit)
and you lost access to the cool 512 GB RAM computer as a result. Is that the
end of the world?

Not really. Instead of relying on computer memory, you can build the graph in
your hard drive. The access will not be as fast as the RAM-bases graph, but
something is better than nothing. In fact, Hadoop technology [discussed
earlier in our blog](http://www.homolog.us/blogs/category/hadoop/) indeed
makes such a move. Moreover, a hard disk based method is immensely scalable,
whereas adding RAM does not scale well unless your country has a no limit
credit card :)

One easy way to build the graph is to use [SQL
database](http://www.sqlite.org/), where you add each node as a new entry.
Each entry will have two fields - 'node' and 'next'. Then you need to create
an index over the nodes to traverse through any part of the graph rapidly.

That solution may work, but SQL databases were originally designed to hold
large number of names, addresses and credit card numbers, not to store graphs.
Therefore, the access to nodes and traversing through the graph will not be
very fast, once your graph crosses a critical size. In fact, the indexing step
itself can take very long for a large graph.

Over the last ten years, internet companies encountered other similar
problems, where they realized that graph-friendly databases were needed. Thus
came NOSQL databases. All that the bioinformatics community needs to do is to
leverage on an existing infrastructure.

We are currently exploring [neo4j](http://www.meetup.com/graphdb-
madrid/events/46980642/) and HBase, but many other graph-friendly NOSQL
databases exist. A full list is [available
here](http://en.wikipedia.org/wiki/NoSQL).

\--------------

External links -

[A different view on NOSQL databases](http://bjclark.me/2009/08/nosql-if-only-
it-was-that-easy/)

