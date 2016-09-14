---
title: Are Graph Databases Ready for Bioinformatics?
tags: []
categories:
- blog
---
Many many months back, we looked into NoSQL databases for storing de Bruijn
graph structure and [mentioned about them
here](http://www.homolog.us/blogs/blog/2012/06/08/nosql-databases-for-
bioinformatics/). Bioinformatics tools often use graph structures for storing
various data sets. Some of those graphs are fairly large and need to be
traversed quickly. Unlike traditional SQL databases, which are fairly slow for
graphs, [NoSQL databases like Neo4j](http://www.neo4j.org/) seem to focus on
rapid graph traversal as their main goal.
<!--more-->

A new editorial article - ["Are graph databases ready for bioinformatics?"](ht
tp://bioinformatics.oxfordjournals.org/content/early/2013/10/21/bioinformatics
.btt549.full) \- published in Bioinformatics by Christian Theil Have1 and Lars
Juhl Jensen shines more light on the same topic.

Their conclusion -

> In summary, graph databases themselves are ready for bioinformatics and can
offer great speedups over relational databases on selected problems. The fact
that a certain dataset is a graph, however, does not necessarily imply that a
graph database is the best choice; it depends on the exact types of queries
that need to be performed. Graph queries formulated in terms of paths can be
concise and intuitive compared with equivalent SQL queries complicated by
joins. Nevertheless, declarative graph query languages leave much to be
desired, both feature-wise and performance-wise. Relational databases are a
better choice when set operations are needed. Such operations are not as
natural a fit to graph databases and have yet to make it into declarative
graph database query languages. These languages are efficient for basic path
traversal problems, but to realize the full benefits of using a graph
database, it is presently necessary to tightly integrate the relevant
algorithms with the graph database.

Speaking of de Bruijn graphs, our conclusion in early 2012 was that graph
databases were too bulky for genome assembly.

