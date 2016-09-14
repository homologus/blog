---
title: 'After HGAP And SPAdes Comes New PacBio Assembler - MHAP '
tags: []
categories:
- blog
---
Adam Phillippy and collaborators submitted a new paper to biorxiv -
<!--more-->

[Assembling Large Genomes with Single-Molecule Sequencing and Locality
Sensitive Hashing](http://biorxiv.org/content/early/2014/08/14/008003)

> We report reference-grade de novo assemblies of four model organisms and the
human genome from single-molecule, real-time (SMRT) sequencing. Long-read SMRT
sequencing is routinely used to finish microbial genomes, but the available
assembly methods have not scaled well to larger genomes. Here we introduce the
MinHash Alignment Process (MHAP) for efficient overlapping of noisy, long
reads using probabilistic, locality-sensitive hashing. Together with Celera
Assembler, MHAP was used to reconstruct the genomes of Escherichia coli,
Saccharomyces cerevisiae, Arabidopsis thaliana, Drosophila melanogaster, and
human from high-coverage SMRT sequencing. The resulting assemblies include
fully resolved chromosome arms and close persistent gaps in these important
reference genomes, including heterochromatic and telomeric transition
sequences. For D. melanogaster, MHAP achieved a 600-fold speedup relative to
prior methods and a cloud computing cost of a few hundred dollars. These
results demonstrate that single-molecule sequencing alone can produce near-
complete eukaryotic genomes at modest cost.

A few comments -

**1\. Primary innovation**

They use [MinHash sketch](http://en.wikipedia.org/wiki/MinHash).

> In computer science, MinHash (or the min-wise independent permutations
locality sensitive hashing scheme) is a technique for quickly estimating how
similar two sets are. The scheme was invented by Andrei Broder (1997),[1] and
initially used in the AltaVista search engine to detect duplicate web pages
and eliminate them from search results.[2] It has also been applied in large-
scale clustering problems, such as clustering documents by the similarity of
their sets of words.[1]

...

A large scale evaluation has been conducted by Google in 2006 [10] to compare
the performance of Minhash and Simhash[11] algorithms. In 2007 Google reported
using Simhash for duplicate detection for web crawling[12] and using Minhash
and LSH for Google News personalization.[13]

Here is a figure from the paper, explaining how it works -

![Capture](http://www.homolog.us/blogs/wp-content/uploads/2014/08/Capture-
229x300.png)

**2\. SPAdes vs MHAP comparison**

> Using PBcR-MHAP, microbial genomes can be completely assembled from long
reads in roughly the same time required to generate incomplete assemblies from
short reads. For example, PBcR-MHAP was able to accurately resolve the entire
genome of E. coli K12 using 85X of SMRT reads in 4.6 CPU hours, or 20 minutes
using a modern 16-core desktop computer. In comparison, the state-of-the-art39
SPAdes assembler40 required 4.1 CPU hours to assemble 85X Illumina reads from
the same genome. Both short- and longread assemblies are highly accurate at
the nucleotide level (>99.999%), but the short-read assembly is heavily
fragmented and contains more structural errors (Supplementary Table S4,
Supplementary Fig. S3). Our initial SMRT assembly does contain more single-
base insertion/deletion (Indel) errors, but polishing it with Quiver
(requiring an additional 6.6 CPU hours) resulted in the lowest number of
consensus errors of all assemblies (11 vs. 96 for SPAdes).

**3\. Assembly cost**

> Exponentially lower costs have democratized DNA sequencing, but assembling a
large genome still requires substantial computing resources. Cloud computing
services offer an alternative for researchers that lack access to
institutional computing resources. However, the cost of assembling long-read
data using cloud computing has been prohibitive. For example, using Amazon Web
Services (AWS), the estimated cost to generate the D. melanogaster PBcR-BLASR
assembly is over $100,000 at current rates, an order of magnitude higher than
the sequencing cost. With MHAP, this cost is drastically reduced to under
$300. To expand access to the PBcR-MHAP assembly pipeline, we have provided a
free public AWS image as well as supporting documentation for non-expert users
that reproduces the D. melanogaster assembly presented here in less than 10
hours using AWS. Allocating additional compute nodes, which would marginally
increase costs, could further reduce assembly time. For E. coli, the total
cost of PBcR-MHAP assembly and Quiver polishing is currently less than $2.
With MHAP, assembly costs are now a small fraction of the sequencing cost for
most genomes, making long-read sequencing and assembly more widely accessible.

**4\. Overall assessment**

a) The introduction of MinHash sketch in assembly is very innovative. Also, it
is very helpful that they gave full demonstration of their assembly technique
for small and large genomes.

b) Aligner comparison -

> In addition to speed, MHAP is a highly sensitive overlapper. We evaluated
the sensitivity and specificity of MHAP versus BLASR32, the only other aligner
currently capable of overlapping SMRT reads. BWA-MEM, SNAP, and RazerS were
also evaluated, but their current versions were unable to reliably detect
noisy overlaps (Supplementary Note 2).

Not sure, why they overlooped DALIGN. Also, BWA-MEM is tuned to near perfect
alignment (k=19) and a small change in parameter will give what they are
looking for. So, "their current versions were unable to reliably detect noisy
overlaps" can be easily and painlessly corrected by sending a quick email to
Heng Li.

c) The cost section is somewhat sloppy and is probably written for marketing
department of PacBio, not serious audience. Why is cloud cost of E. coli given
with Quiver and Drosophila without Quiver? Also, what can one project from
$300 for Drosophila to the cloud cost of assembling human-sized genome using
the same method? Does it grow as O(N) or O(N^2) with respect to size? We do
not need exact numbers, but the order of growth of assembly time with genome
size is something any user will look for.

Edit. A comment from @aphillippy

![Capture](http://www.homolog.us/blogs/wp-
content/uploads/2014/08/Capture1-300x53.png)

d) With regard to the general field of bioinformatics, it is indeed great news
that assembling complete genomes, which is one of the long-standing problems,
is going to be solved satisfactorily. That means bioinformaticians will have
to rethink their strategy for future -

[Bioinformatics at a Crossroad Again Which Way
Next?](http://www.homolog.us/blogs/blog/2014/08/11/bioinformatics-at-a
-crossroad-again-which-way-next/)

