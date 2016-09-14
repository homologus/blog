---
title: Ways to Find Homologous Genes
tags: []
categories:
- blog
---
The focus of this commentary is sequence homology defined as shared ancestry
between two segments of sequences. It includes two broad classes of relations
between genes - orthology and paralogy. Lately Ken Wolffe added a new term
'ohnology' to describe paralogous genes, whose shared ancestry is from whole
genome duplication events. As an example, [bladderwort genome
paper](http://www.homolog.us/blogs/2013/05/12/carnivorous-bladderwort-plant-
genome-shows-some-designers-are-more-intelligent-than-others/) presents very
informative analysis of various whole genome duplication event in plants.
Check [their Fig. 1](http://www.nature.com/nature/journal/vaop/ncurrent/fig_ta
b/nature12132_F1.html) for example.
<!--more-->

**Orthology**

Orthology refers to shared ancestry of a gene in two species. For example,
human hox genes in four genomic clusters have orthologies with four sets of
hox genes.

**Paralogy**

Paralogy refers to shared ancestry caused by gene duplication. Hox1, Hox2,
Hox3 and Hox4 clusters in human genome are paralogous to each other.

\-------------------------------------

Now that large number of complete genome sequences are being published online,
we checked for best approaches to find orthologous genes in those genomes and
came across a very informative Biostars thread.

[What is the best method to find orthologous genes of a
species?](http://www.biostars.org/p/7568/#7611)

Rest of this commentary is our lame attempt to summarize excellent discussions
in the above thread.

**Bioinformatics approaches for finding orthologies**

They fall into two categories - **reciprocal BLAST** and **construction of
phylogenetic trees**. Reciprocal BLAST approach is fast and less accurate, and
phylogenetic tree approach is slow and more accurate.

[BlastO](http://oxytricha.princeton.edu/BlastO/) is a BLAST web-service
developed by Princeton researcher Yi Zhou to allow you to do BLAST on
orthologous genes.

\------------------------------------------

**Databases**

Several online databases exist, from where researchers can download pre-
computed orthology tables for a set of organisms.

**MetaPhOrs**

[MetaPhOrs](http://orthology.phylomedb.org/) can be described as a orthology
database of orthology databases. It combines results from many other BLAST-
based orthology databases using phylogeny-based method and develops more
accurate tables.

> MetaPhOrs is a public repository of phylogeny-based orthology and paralogy
predictions that were computed using resources available in seven popular
homology prediction services (PhylomeDB, EnsemblCompara, EggNOG, OrthoMCL,
COG, Fungal Orthogroups, and TreeFam).

MetaPhOrs data can be downloaded from [this ftp
site](ftp://phylomedb.org/metaphors/). We do not know how often they update
their tables, because keeping up with the newly released genomes is the
biggest challenge faced by all groups maintaining orthology databases.
Currently it includes 863 organisms, but a large number of them are
prokaryotes.

**COG and eggNOG**

[COG database](http://www.ncbi.nlm.nih.gov/COG/) is maintained at NCBI.

> Clusters of Orthologous Groups of proteins (COGs) were delineated by
comparing protein sequences encoded in complete genomes, representing major
phylogenetic lineages. Each COG consists of individual proteins or groups of
paralogs from at least 3 lineages and thus corresponds to an ancient conserved
domain.

FTP site for COG eukaryotic data is
[here](ftp://ftp.ncbi.nih.gov/pub/COG/KOG/). Its eukaryotic cluster includes
only seven organisms.

[EggNOG](http://eggnog.embl.de/version_3.0/) is EMBL's improvement over COG.

> EggNOG (evolutionary genealogy of genes: Non-supervised Orthologous Groups)
is a database of orthologous groups of genes. The orthologous groups are
annotated with functional description lines (derived by identifying a common
denominator for the genes based on their various annotations), with functional
tags: []
categories (i.e derived from the original COG/KOG categories).

eggNOG's database currently counts 721,801 orthologous groups in 1133 species,
covering 4,396,591 proteins (built from 5,214,234 proteins).

Their data can be downloaded from
[here](http://eggnog.embl.de/version_3.0/downloads.html).

**EnsemblCompara**

[EnsemblCompara](http://uswest.ensembl.org/info/docs/compara/index.html) does
very extensive work of building trees for orthologous genes. We do not know
how much they differ from eggNOG, because we are too lazy to read the papers.
Biostars thread says that Ensembl is phylogeny based and eggNOG is BLAST-
based, but the download page of eggNOG does list some trees.

> Gene trees are constructed using a representative protein for every gene in
Ensembl: proteins are clustered using hcluster_sg based on WU-BLAST scores,
and each cluster of proteins is aligned using M-Coffee. Finally, TreeBeST is
used to produce a gene tree from each multiple alignment, reconciling it with
the species tree to call duplication events. Homologues are deduced from these
trees. We also determine gene gain and loss events using the CAFE software.

\------------------------------------------------

Possibly not being updated:

**InParanoid and MultiParanoid**

[InParanoid](http://inparanoid.sbc.su.se/cgi-bin/index.cgi) was last updated
in June 2009, when nobody expected more than five Illumina machines to be
sold. [MultiParanoid](http://multiparanoid.sbc.su.se/) was last updated three
years prior to that. Oh well.

OrthoMCL, phylofacts, TreeFam, PHOG - are they being updated?

If we like to use a database being updated regularly with arrival of new
genomes from all kinds of places, which one should we use?

