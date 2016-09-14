---
title: Apache Spark
tags: []
categories:
- blog
---
Yesterday I attended a seminar on [Apache Spark](http://spark.apache.org/),
and thought the readers may find this new technology interesting for their
programming and data analysis. There is no bioinformatics connection at the
moment, and I am simply mentioning it as a type of fault-tolerant software-
hardware technology with a lot of development work going on, and may turn out
to be useful in the future.
<!--more-->

How good is spark? [An example](https://databricks.com/blog/2014/11/05/spark-
officially-sets-a-new-record-in-large-scale-sorting.html) \-

> A month ago, we shared with you our entry to the 2014 Gray Sort competition,
a 3rd-party benchmark measuring how fast a system can sort 100 TB of data (1
trillion records). Today, we are happy to announce that our entry has been
reviewed by the benchmark committee and we have officially won the Daytona
GraySort contest!

In case you missed our earlier blog post, using Spark on 206 EC2 machines, we
sorted 100 TB of data on disk in 23 minutes. In comparison, the previous world
record set by Hadoop MapReduce used 2100 machines and took 72 minutes. This
means that Spark sorted the same data 3X faster using 10X fewer machines. All
the sorting took place on disk (HDFS), without using Sparks in-memory cache.
This entry tied with a UCSD research team building high performance systems
and we jointly set a new world record.

Description of the technology from wiki -

> Apache Spark is an open source cluster computing framework originally
developed in the AMPLab at University of California, Berkeley but was later
donated to the Apache Software Foundation where it remains today. In contrast
to Hadoop's two-stage disk-based MapReduce paradigm, Spark's multi-stage in-
memory primitives provides performance up to 100 times faster for certain
applications.[1] By allowing user programs to load data into a cluster's
memory and query it repeatedly, Spark is well-suited to machine learning
algorithms.[2]

Spark requires a cluster manager and a distributed storage system. For cluster
management, Spark supports standalone (native Spark cluster), Hadoop YARN, or
Apache Mesos.[3] For distributed storage, Spark can interface with a wide
variety, including Hadoop Distributed File System (HDFS),[4] Cassandra,[5]
OpenStack Swift, Amazon S3, Kudu, or a custom solution can be implemented.
Spark also supports a pseudo-distributed local mode, usually used only for
development or testing purposes, where distributed storage is not required and
the local file system can be used instead; in such a scenario, Spark is run on
a single machine with one executor per CPU core.

<iframe width="560" height="315" src="http://www.youtube.com/embed/qLvLg-sqxKc" frameborder="0"> </iframe>

