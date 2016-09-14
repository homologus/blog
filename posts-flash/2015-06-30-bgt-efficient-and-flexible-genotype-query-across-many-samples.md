---
title: 'BGT: Efficient and Flexible Genotype Query Across Many Samples'
tags: []
categories:
- blog
---
Heng Li posted a new paper at [arxiv](http://arxiv.org/abs/1506.08452) on BGT
format, which "stores the integer matrix as two positional BWTs (PBWTs), one
for the lower bit and the other for the higher bit."
<!--more-->

**The problem -**

> VCF/BCF (Danecek et al., 2011) is the primary format for storing and
analyzing genotypes of multiple samples. It however has a few issues. Firstly,
as a streaming format, VCF compresses all types of information together.
Retrieving site annotations or the genotypes of a few samples usually requires
to decode the genotypes of all samples, which is unnecessarily expensive.
Secondly, VCF does not take advantage of linkage disequilibrium (LD), while
using this information can dramatically improve compression ratio (Durbin,
2014). Thirdly, a VCF record is not clearly defined. Each record may consist
of multiple alleles with each allele composed of multiple SNPs and INDELs.
This ambiguity complicates annotations, query of alleles and integration of
multiple data sets. At last, most existing VCF-based tools do not support
expressive data query. We frequently need to write scripts for advanced
queries, which costs both development and processing time. GQT (Layer et al.,
2015) attempts to solve some of these issues. While it is very fast for
selecting a subset of samples and for traversing all sites, it discards
phasing, is inefficient for region query and is not compressed well. The
observations of these limitations motivated us to develop BGT.

**The solution -**

> Summary: BGT is a compact format, a fast command line tool and a simple web
application for efficient and convenient query of whole-genome genotypes and
frequencies across tens to hundreds of thousands of samples. On real data, it
encodes the haplotypes of 32,488 samples across 39.2 million SNPs into a 7.4GB
database and decodes a couple of hundred million genotypes per CPU second. The
high performance enables real-time responses to complex queries.

Availability and implementation: [here](https://github.com/lh3/bgt)

