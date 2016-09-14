---
title: If You Want to Take Your Bioinformatics Analysis to the Cloud
tags: []
categories:
- blog
---
[A paper published in Biology Direct](http://www.biology-
direct.com/content/7/1/43/abstract) by Lin Dai, Xin Gao, Yan Guo, Jingfa Xiao
and Zhang Zhang provides a good list of programs that are currently available.
(h/t: @sgivan)
<!--more-->

> **Data as a Service (DaaS)**

[AWS](http://aws.amazon.com/publicdatasets): Public Datasets Cloud-based
archives of GenBank, Ensembl, 1000 Genomes, Model Organism Encyclopedia of DNA
Elements, Unigene, Influenza Virus, etc.

\--------

**Software as a Service (SaaS)**

[BGI Cloud](http://cloud.genomics.cn) Cloud-based implementations of various
genomic analysis applications

[CloudAligner](http://cloudaligner.sourceforge.net) Fast and full-featured
MapReduce-based tool for sequence mapping

[CloudBLAST](http://ammatsun.acis.ufl.edu/amwiki/index.php/CloudBLAST_Project)
A cloud-based implementation of NCBI BLAST

[CloudBurst](http://cloudburst-bio.sourceforge.net) Highly sensitive short
read mapping with MapReduce

[Contrail](http://contrail-bio.sourceforge.net) Cloud-based de novo assembly
of large genomes

[Crossbow](http://bowtie-bio.sf.net/crossbow) Read Mapping and SNP calling
using cloud computing

[EasyGenomics](http://www.easygenomics.org) Cloud-based NGS pipelines for
whole genome resequencing, exome resequencing, RNA-Seq, small RNA and de novo
assembly

[eCEO](http://www.comp.nus.edu.sg/~wangzk/eCEO.html) Cloud-based
identification of large-scale epistatic interactions in genome-wide
association study (GWAS)

[FX](http://fx.gmi.ac.kr) RNA-Seq analysis tool

[Gaea](http://bgiamericas.com/data-analysis/cloud-computing) Cloud-based
genome re-sequencing assembly

[Hecate](http://bgiamericas.com/data-analysis/cloud-computing) (unpublished)
Cloud-based de novo assembly

[Jnomics](http://sourceforge.net/apps/mediawiki/jnomics) (unpublished) Cloud-
scale sequence analysis suite based on Apache Hadoop

[Myrna](http://bowtie-bio.sourceforge.net/myrna) Differential gene expression
tool for RNA-Seq

[PeakRanger](http://www.modencode.org/software/ranger) Cloud-enabled peak
caller for ChIP-seq data

[RSD](http://roundup.hms.harvard.edu): Reciprocal smallest distance algorithm
for ortholog detection using Amazon's Elastic Computing Cloud

[VAT](http://vat.gersteinlab.org) Variant annotation tool to functionally
annotate variants from multiple personal genomes at the transcript level

[YunBe](http://tinyurl.com/yunbedownload) Pathway-based or gene set analysis
of expression data

\----------------

**Platform as a Service (PaaS)**

[Eoulsan](http://transcriptome.ens.fr/eoulsan) Cloud-based platform for high
throughput sequencing analyses

[Galaxy Cloud](http://galaxy.psu.edu) Cloud-scale Galaxy for large-scale data
analysis

\--------------------

**Infrastructure as a Service (IaaS)**

[Cloud BioLinux](http://cloudbiolinux.org): A publicly accessible virtual
machine for high performance bioinformatics computing using cloud platforms

[CloVR](http://clovr.org): A portable virtual machine for automated sequence
analysis using cloud computing;

One interesting aspect of Biology Direct is that it allows readers to see
reviewers' comments. The following exchange between Dr. Igor Zhulin
(University of Tennessee, United States of America) and the authors
illucidates on HPC versus cloud issues.

>

**Reviewer 2**: The review summarizes advantages of using cloud computing for big data storage and analysis issues in bioinformatics. In general, it does a fair job on this front. However, disadvantages of clouds are not discussed in this review at all. For example, time-critical calculations, complex tasks that require data management (load balancing, fault tolerance issues, etc.) will not do well on clouds that lack the edge of advanced HPC architectures. 

**Authors response**: Thanks for your valuable comments. We accepted your comments and added some description in the main text. Hadoop (http://hadoop.apache.org) features two key modulesMapReduce and Hadoop Distributed File System (HDFS). MapReduce divides a computational program into many small sub-problems and distributes them on multiple computer nodes, and HDFS provides a distributed file system that stores data on these nodes. Hadoop and its associated software are designed to handle load balancing among multiple nodes and to detect node failures that can be automatically re-executed on any node. Therefore, Hadoop is capable of performing time-critical calculations by distributing tasks and large datasets over multiple computer nodes, supporting big data scaling, and enabling fault-tolerant parallelized analysis.

\---------------

Edit.

In the context of doing Bioinformatics in the cloud, it is worth mentioning
that our long time reader Mikael Huss maintains a highly informative blog
([Follow the Data](http://followthedata.wordpress.com/)). Mikael suggests
looking into Hadoop-based program [Seal](http://biodoop-seal.sourceforge.net/)
for doing similar tasks as Jnomics, namely cloud-scale sequence analysis.

