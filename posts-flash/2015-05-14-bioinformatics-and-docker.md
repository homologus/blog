---
title: Bioinformatics and Docker
tags: []
categories:
- blog
---
Since it is our lightweight algorithm day, we thought it would be worthwhile
to mention several relevant posts on Docker.
<!--more-->

**1\. What is Docker?**

Docker is a lightweight way to introduce portability in the code. It helps you
containerize a code module tested on an operating system, and not run a
separate VMware virtualization installation for every new module.

The following slides introduce you to Docker. Especially pay attention to the
'matrix from hell' slide.

[slideshare id=27669368&doc;=introdockeroctober13-131028203253-phpapp02]

**2\. Docker in Bioinformatics**

<iframe width="560" height="315" src="http://www.youtube.com/embed/Y59uhI0b1CA" frameborder="0"> </iframe>

Docker is being used to containerize bioinformatics codes and there is already
a [biodocker project](http://biodocker.github.io/).

A few days back, redditers asked - [Does Docker hit performance of
bioinformatics algorithms?](http://www.reddit.com/r/bioinformatics/comments/2f
6cnx/question_does_using_docker_hit_performance/)

The following blog post from Heng Li would be informative in that respect.

[A few hours with docker](http://lh3.github.io/2015/04/25/a-few-hours-with-
docker/)

>

**Preliminary thoughts**

Docker is a bless to complex systems such as the old Apache+MySQL+PHP combo,
but is a curse to simple command line tools. For simple tools, it adds
multiple complications (security, kernel version, Dockerfile, large package,
inter-process communication, etc) with little benefit.

Bioinformatics tools are not rocket science. They are supposed to be simple.
If they are not simple, we should encourage better practices rather than live
with the problems and resort to docker. I am particularly against dockerizing
easy-to-compile tools such as velvet and bwa or well packaged tools such as
spades. Another large fraction of tools in C/C++ can be compiled to statically
linked binaries or shipped with necessary dynamic libraries (see salifish).
While not ideal, these are still better solutions than docker. Docker will be
needed for some tools with complex dependencies, but I predict most of such
tools will be abandoned by users unless they are substantially better than
other competitors, which rarely happens in practice.

PS: the only benefit of dockerizing simple tools is that we can acquire a tool
with docker pull user/tool, but that is really the benefit of a centralized
repository which we are lacking in our field.

Our view is in agreement with Heng Li's last paragraph ("PS"), but Docker will
likely have a different use in the bioinformatics world. More on that in a
later blog post.

\----------------------------

Edit.

Adding a few other useful links -

1\. Dockerized bioinformatics programs at
[biostar](https://www.biostars.org/p/117401/)

2\. [Benchmarking variation and RNA-seq analyses on Amazon Web Services with
Docker](http://bcb.io/2014/12/19/awsbench/)

> We developed a freely available, easy to run implementation of bcbio-nextgen
on Amazon Web Services (AWS) using Docker. bcbio is a community developed tool
providing validated and scalable variant calling and RNA-seq analysis. The AWS
implementation automates all of the steps of building a cluster, attaching
high performance shared filesystems, and running an analysis. This makes bcbio
readily available to the research community without the need to install and
configure a local installation.

The entire installation bootstraps from standard Linux AMIs, enabling
adjustment of the tools, genome data and installation without needing to
prepare custom AMIs. The implementation uses Elasticluster to provision and
configure the cluster. We automate the process with the boto Python interface
to AWS and Ansible scripts. bcbio-vm isolates code and tools inside a Docker
container allowing runs on any remote machine with a download of the Docker
image and access to the shared filesystem. Analyses run directly from S3
buckets, with automatic streaming download of input data and upload of final
processed data.

We provide timing benchmarks for running a full variant calling analysis using
bcbio on AWS. The benchmark dataset was a cancer tumor/normal evaluation, from
the ICGC-TCGA DREAM challenge, with 100x coverage in exome regions. We
compared the results of running this dataset on 2 different networked
filesystems: Lustre and NFS. We also show benchmarks for an RNA-seq dataset
using inputs from the Sequencing Quality Control (SEQC) project.

3\. Docker guide at [basespace](https://developer.basespace.illumina.com/docs/
content/documentation/native-apps/manage-docker-image)

