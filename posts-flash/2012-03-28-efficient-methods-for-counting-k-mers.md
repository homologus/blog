---
title: Efficient Methods for Counting K-mers
tags:
- K-mer
categories:
- blog
---
For new readers, easiest way to follow us is through our [twitter
feed](https://twitter.com/#!/homolog_us/). The feed is updated, whenever we
post a commentary here.
<!--more-->

Usually, when we receive a new genomic or transcriptomic read library, we
generally like to check k-mer distribution before performing assemblies or
other serious analysis. A number of efficient k-mer counting algorithms have
been publicly available, and all of them give out easily compilable source
codes.

**A. Bloom Filter-based Approach**

This method uses the fact that, in real data, large number of k-mers are
singletons appearing due to sequencing errors. Bloom filter based approach
takes the least amount of memory, but is slightly slower than JELLYFISH
hashing approach.

i) [Efficient counting of k -mers in DNA sequences using a bloom filter, Pll
Melsted and Jonathan K Pritchard, BMC Bioinformatics 2011, 12:333
doi:10.1186/1471-2105-12-333.](http://www.biomedcentral.com/1471-2105/12/333)

[BFcounter code is here.](http://pritch.bsd.uchicago.edu/bfcounter.html)

ii) [khmer](http://ivory.idyll.org/blog/jul-10/kmer-filtering),
[code](http://ged.msu.edu/angus/metag-assembly-2011/khmer-scripts.html)

**B. Hashing-based Approach as in JELLYFISH **

i) [Guillaume Marcais and Carl Kingsford, A fast, lock-free approach for
efficient parallel counting of occurrences of k-mers. Bioinformatics (2011)
27(6): 764-770 doi:10.1093/bioinformatics/btr011.](http://www.cbcb.umd.edu/sof
tware/jellyfish/)

> It is based on a multithreaded, lock-free hash table optimized for counting
k-mers up to 31 bases in length. Due to their flexibility, suffix arrays have
been the data structure of choice for solving many string problems. For the
task of k-mer counting, important in many biological applications, Jellyfish
offers a much faster and more memory-efficient solution.

Their manual is available [here](http://www.cbcb.umd.edu/software/jellyfish
/jellyfish-manual-1.1.pdf).

**C. Meryl**

We are not sure of how efficient the algorithm is. Their website says -

> An out-of-core k-mer counter. The amount of sequence that can be processed
for any size k depends only on the amount of free disk space.

More [here.](http://sourceforge.net/apps/mediawiki/kmer/index.php?title=Gettin
g_Started_with_Meryl)

**D. Tallymer - Suffix array based approach**

[A new method to compute K-mer frequencies and its application to annotate
large repetitive plant genomes

Stefan Kurtz, Apurva Narechania, Joshua C Stein and Doreen Ware, BMC Genomics,
2008, 9:517 doi:10.1186/1471-2164-9-517.

