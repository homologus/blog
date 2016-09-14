---
title: A Strategy for Running Trinity on Very Large NGS Library or Reducing Number
  of Genes
tags: []
categories:
- rnaseq
---
For new readers, easiest way to follow us is through our [twitter
feed](https://twitter.com/#!/homolog_us/). The feed is updated, whenever we
post a commentary here.
<!--more-->

One of the readers in our forum asked about [how to reduce Oases transcripts
into smaller number of
unigenes](http://www.homolog.us/smf/index.php?topic=64.0). We have been
grappling with the same problem and have not come up with a good strategy yet.
Here is what we have done so far. We would welcome innovative ideas from
others.

**Initial Trinity run** \- We have seven HiSeq RNAseq libraries with a total of about 700 million reads. In a perfect world, we would send all reads to a gigantic computer with unlimited RAM and run Trinity on the entire set. However, that is not possible in real world, and we ended up running Trinity with each of the sets. As a result, we had ~500,000 genes with many redundancies. 

**Abundance sorting** \- In the next step, we aggregated all 700 million reads into one file, and ranked them in decreasing order of their occurrences. One read appeared 138,000 times, many appeared ~1000 times and the largest number of reads appeared only once. Those frequencies are related to the genes they match with. 

**Shortlisting of genes** \- Next, we aligned those reads with the set of 500,000 genes produced by Trinity using Bowtie, and picked the longest gene for each read starting from the top (i.e. most abundant). We also marked each of the gene to not be further considered in our analysis. For example, if the most abundant read matched with GENE1, GENE2, GENE3 and GENE2 is the longest, GENE2 is picked for our reduced set, and GENE1, GENE3 are flagged to be not considered further down the list. We also picked an abundance threshold for reads, and selected ~48,000 genes for our shortlist. Overall, all 500,000 genes had a coverage of 92% among the reads, whereas the reduced set of 48,000 genes had coverage of 80%. Therefore, it seems like we managed to reduce the gene count substantially without losing many of the reads. 

**Refinement of structures** \- In the subsequent step, we went through all reads and compared k-mers (k=25 for our calculation) with the shortlisted genes. The reads are partitioned into 48,000 sets according to their k-mer matches with the genes. We ran Trinity with each of the 48,000 sets and determined refined structures, if any, for those genes. 

**Final Trinity** \- Finally, we ran Trinity on reads that were not covered by the above genes to find any gene that we missed. However, the method of analysis suggests that the genes identified in this step are of low abundance, and we can focus the initial analysis on the 48,000 high abundance genes before delving into this later set.

