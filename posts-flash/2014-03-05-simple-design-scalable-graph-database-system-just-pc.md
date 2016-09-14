---
title: Simple Design for a Scalable Graph Database System &ndash; on Just a PC
tags: []
categories:
- blog
---
@infoecho forwarded this arxiv paper that our readers may find interesting.
Scaffolding in genome assembly is the problem we have in mind. The scaffolding
graph can get big and it also possibly follows power-law distribution in terms
of connectivities. @infoecho is likely looking at the possibility of storing a
large string graph for PacBio assembly.
<!--more-->

[GraphChi-DB: Simple Design for a Scalable Graph Database System -- on Just a
PC](http://arxiv.org/pdf/1403.0701v1.pdf)

> We propose a new data structure, Parallel Adjacency Lists (PAL), for
efficiently managing graphs with billions of edges on disk. The PAL structure
is based on the graph storage model of GraphChi (Kyrola et. al., OSDI 2012),
but we extend it to enable online database features such as queries and fast
insertions. In addition, we extend the model with edge and vertex attributes.
Compared to previous data structures, PAL can store graphs more compactly
while allowing fast access to both the incoming and the outgoing edges of a
vertex, without duplicating data. Based on PAL, we design a graph database
management system, GraphChi-DB, which can also execute powerful analytical
graph computation. We evaluate our design experimentally and demonstrate that
GraphChi-DB achieves state-of-the-art performance on graphs that are much
larger than the available memory. GraphChi-DB enables anyone with just a
laptop or a PC to work with extremely large graphs.

