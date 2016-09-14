---
title: De Novo Assembly of Human Genome with Only 1.5 GB RAM
tags: []
categories:
- blog
---
We alluded to the latest and greatest paper by Rayan Chikhi, Antoine Limasset,
Shaun Jackman, Jared Simpson and Paul Medvedev in an earlier blog post
("[Bounds from a Card Trick](http://www.homolog.us/blogs/blog/2014/01/16
/bounds-card-trick/)"). Now you can read their actual paper at arxiv.
<!--more-->

[On the representation of de Bruijn graphs](http://arxiv.org/abs/1401.5383)

> The de Bruijn graph plays an important role in bioinformatics, especially in
the context of de novo assembly. However, the representation of the de Bruijn
graph in memory is a computational bottleneck for many assemblers. Recent
papers proposed a navigational data structure approach in order to improve
memory usage. We prove several theoretical space lower bounds to show the
limitation of these types of approaches. We further design and implement a
general data structure (DBGFM) and demonstrate its use on a human whole-genome
dataset, achieving space usage of 1.5 GB and a 46% improvement over previous
approaches. As part of DBGFM, we develop the notion of frequency-based
minimizers and show how it can be used to enumerate all maximal simple paths
of the de Bruijn graph using only 43 MB of memory. Finally, we demonstrate
that our approach can be integrated into an existing assembler by modifying
the ABySS software to use DBGFM.

The paper has three unusual/innovative concepts. Two of those are technical.

i) Minimizers from Jim Yorke's old papers to reduce the k-mers into linear
chains.

[Roberts, M., Hayes, W., Hunt, B.R., Mount, S.M., Yorke, J.A.: Reducing
storage requirements for biological sequence comparison. Bioinformatics
20(18), 33633369
(2004).](http://bioinformatics.oxfordjournals.org/content/20/18/3363.abstract)

[Roberts, M., Hunt, B.R., Yorke, J.A., Bolanos, R.A., Delcher, A.L.: A
preprocessor for shotgun assembly of large genomes. Journal of Computational
Biology 11(4), 734752 (2004).](http://citeseerx.ist.psu.edu/viewdoc/download?d
oi=10.1.1.84.1218&rep=rep1&type=pdf)

ii) Traversal of those linear chains through a data structure built on FM
index.

The third unusual aspect of the paper is that it cites a [blog post on succint
de Bruijn graph from Alex Bowe](http://alexbowe.com/succinct-debruijn-graphs/)
!! We have seen citations of arxiv preprints in the past, but citations of
blog posts is novel.

\-----------------------------------------------------------------------------
-

Edit.

Useful information for those planning to implement the algorithm -

> There are several implementation details that make the algorithm practical.

First, reverse complements are supported in the natural way by identifying
each k-mer with its reverse complement and letting the minimizer be the
smallest l-mer in both of them.

Second, we avoid creating 4^l files, which may be more than the file system
supports. Instead, we use virtual files and group them together into a smaller
number of physical files. This allowed us to use l = 10 in our experiments.

Third, when we load a file from disk (line 7) we only load the first and last
k-mer of each string, since the middle part is never used by the compaction
algorithm. We store the middle part in an auxiliary file and use a pointer to
keep track of it within the strings in the Fm files.

Consequently, the algorithm memory usage depends on the number of strings in
each file Fm, but not on the total size of those files. For a fixed input S,
the number of strings in a file Fm depends on the minimizer length l and the
ordering of minimizers. When l increases, the number of (k-1)-mers in S that
have the same minimizer decreases. Thus, increasing l yields less strings per
file, which decreases the memory usage. We also realized that, when highly-
repeated l-mers are less likely to be chosen as minimizers, the sequences are
more evenly distributed among files. We therefore perform in-memory l-mer
counting (line 3) to obtain a sorted frequency table of all l-mers. This step
requires an array of 64S^l bits to store the count of each l-mer in 64 bits,
which is negligible memory overhead for small values of l (8 MB for l = 10).
Each l-mer is then mapped to its rank in the frequency array, to create a
total ordering of minimizers (line 4). Our experiments showed a drastic
improvement over lexicographic ordering (results in Section 9).

Also, RECOMB slides from Rayan -

![Capture](http://www.homolog.us/blogs/wp-
content/uploads/2014/01/Capture6-300x202.png)

