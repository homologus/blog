---
title: Algorithms for Constructing of Phylogenetic Network (Reticulate Evolution)
tags: []
categories:
- blog
---
Professor Dan Graur is writing a book on genome evolution and kindly shared
with us the text on reticulate evolution. Those with computational and
mathematical training may find this field intellectually exciting, because -
<!--more-->

> The methodology for reconstructing phylogenetic networks from empirical data
is still in its infancy despite a veritable deluge of publications on the
subject (e.g., Nakhleh et al. 2005, 2008; Huson and Bryant 2006; Jin et al.
2006, 2007; Than et al. 2008; Willson 2008; Meng and Kubatko 2009; Nakhleh
2009; Huson et al. 2009, 2011; Huson and Scornavacca 2011; Morrison 2011).

We will go through what bioinformatics methods are already available. Please
note that this commentary is not from an expert, and therefore you are advised
to do your due diligence.

Firstly, what is the problem?

In a 2009 review, Bapteste et al wrote -

[Prokaryotic evolution and the tree of life are two different
things](http://www.biomedcentral.com/content/pdf/1745-6150-4-34.pdf)

Two sentences from reviewer John M. Logsdon, Jr. summarize the main message of
the paper.

> The prokaryotic tree of life is dead!

[snip]

Long live the prokaryotic tree of life!

There you go.

Long answer - availability of genomic data from many prokaryotes show that
prokaryotic evolution cannot be explained in terms of a tree, because the
species had extensive amount of lateral gene transfer in the past.

> Background: The concept of a tree of life is prevalent in the evolutionary
literature. It stems from attempting to obtain a grand unified natural system
that reflects a recurrent process of species and lineage splittings for all
forms of life. Traditionally, the discipline of systematics operates in a
similar hierarchy of bifurcating (sometimes multifurcating) categories. The
assumption of a universal tree of life hinges upon the process of evolution
being tree-like throughout all forms of life and all of biological time. In
multicellular eukaryotes, the molecular mechanisms and species-level
population genetics of variation do indeed mainly cause a tree-like structure
over time. In prokaryotes, they do not. Prokaryotic evolution and the tree of
life are two different things, and we need to treat them as such, rather than
extrapolating from macroscopic life to prokaryotes. In the following we will
consider this circumstance from philosophical, scientific, and epistemological
perspectives, surmising that phylogeny opted for a single model as a holdover
from the Modern Synthesis of evolution.

Results: It was far easier to envision and defend the concept of a universal
tree of life before we had data from genomes. But the belief that prokaryotes
are related by such a tree has now become stronger than the data to support
it. The monistic concept of a single universal tree of life appears, in the
face of genome data, increasingly obsolete. This traditional model to describe
evolution is no longer the most scientifically productive position to hold,
because of the plurality of evolutionary patterns and mechanisms involved.
Forcing a single bifurcating scheme onto prokaryotic evolution disregards the
non-tree-like nature of natural variation among prokaryotes and accounts for
only a minority of observations from genomes.

Conclusion: Prokaryotic evolution and the tree of life are two different
things. Hence we will briefly set out alternative models to the tree of life
to study their evolution. Ultimately, the plurality of evolutionary patterns
and mechanisms involved, such as the discontinuity of the process of evolution
across the prokaryote-eukaryote divide, summons forth a pluralistic approach
to studying evolution.

\-----------------------------------------------------------

What can we do then? Enter the networks ! Below, we will link to a number of
papers from various groups working on developing mathematical methods to
construct phylogenetic networks. More detailed discussion will follow later.

**Huson and Bryant** \- [Application of Phylogenetic Networks in Evolutionary Studies](http://mbe.oxfordjournals.org/content/23/2/254.full.pdf+html)

> The evolutionary history of a set of taxa is usually represented by a
phylogenetic tree, and this model has greatly facilitated the discussion and
testing of hypotheses. However, it is well known that more complex
evolutionary scenarios are poorly described by such models. Further, even when
evolution proceeds in a tree-like manner, analysis of the data may not be best
served by using methods that enforce a tree structure but rather by a richer
visualization of the data to evaluate its properties, at least as an essential
?rst step. Thus, phylogenetic networks should be employed when reticulate
events such as hybridization, horizontal gene transfer, recombination, or gene
duplication and loss are believed to be involved, and, even in the absence of
such events, phylogenetic networks have a useful role to play. This article
reviews the terminology used for phylogenetic networks and covers both split
networks and reticulate networks, how they are de?ned, and how they can be
interpreted. Additionally, the article outlines the beginnings of a
comprehensive statistical framework for applying split network methods. We
show how split networks can represent con?dence sets of trees and introduce a
conservative statistical test for whether the con?icting signal in a network
is treelike. Finally, this article describes a new program, SplitsTree4, an
interactive and comprehensive tool for inferring different types of
phylogenetic networks from sequences, distances, and trees.

**Nakleh** \- [The Probability of a Gene Tree Topology within a Phylogenetic Network with Applications to Hybridization Detection](http://www.plosgenetics.org/article/info%3Adoi%2F10.1371%2Fjournal.pgen.1002660#pgen-1002660-g004)

> Gene tree topologies have proven a powerful data source for various tasks,
including species tree inference and species delimitation. Consequently,
methods for computing probabilities of gene trees within species trees have
been developed and widely used in probabilistic inference frameworks. All
these methods assume an underlying multispecies coalescent model. However,
when reticulate evolutionary events such as hybridization occur, these methods
are inadequate, as they do not account for such events. Methods that account
for both hybridization and deep coalescence in computing the probability of a
gene tree topology currently exist for very limited cases. However, no such
methods exist for general cases, owing primarily to the fact that it is
currently unknown how to compute the probability of a gene tree topology
within the branches of a phylogenetic network. Here we present a novel method
for computing the probability of gene tree topologies on phylogenetic networks
and demonstrate its application to the inference of hybridization in the
presence of incomplete lineage sorting. We reanalyze a Saccharomyces species
data set for which multiple analyses had converged on a species tree
candidate. Using our method, though, we show that an evolutionary hypothesis
involving hybridization in this group has better support than one of strict
divergence. A similar reanalysis on a group of three Drosophila species shows
that the data is consistent with hybridization. Further, using extensive
simulation studies, we demonstrate the power of gene tree topologies at
obtaining accurate estimates of branch lengths and hybridization probabilities
of a given phylogenetic network. Finally, we discuss identifiability issues
with detecting hybridization, particularly in cases that involve extinction or
incomplete sampling of taxa.

**Huson** \- [Computing galled networks from real data](http://bioinformatics.oxfordjournals.org/content/25/12/i85.full.pdf+html)

**Jin/Nakhleh** \- [Ef?cient parsimony-based methods for phylogenetic network reconstruction](http://bioinformatics.oxfordjournals.org/content/23/2/e123.full.pdf+html)

**Huson** \- [Dendroscope 3: An Interactive Tool for Rooted Phylogenetic Trees and Networks](http://sysbio.oxfordjournals.org/content/61/6/1061.full.pdf+html)

**Huson (book)** \- [Phylogenetic Networks: Concepts, Algorithms and Applications](http://books.google.com/books?hl=en&lr=&id=0rB5I5GxveAC&oi=fnd&pg=PR5&ots=B9QB-Gd3HL&sig=QU6xrjII6R1L4v_QUzKx88PbOQk#v=onepage&q&f=false)

**Nakleh (book chapter)** \- [Evolutionary Phylogenetic Networks: Models and Issues](http://www.cs.rice.edu/~nakhleh/Papers/HeathRamakrishnanBookChapter.pdf)

**Nakleh** \- [PhyloNet: a software package for analyzing and reconstructing reticulate evolutionary relationships](http://www.biomedcentral.com/content/pdf/1471-2105-9-322.pdf)

**Morrison** \- [Next generation sequencing and phylogenetic networks](http://journal.embnet.org/index.php/embnetjournal/article/view/760/1103)

**Morrison** \- [free electronic book](http://www.rjr-productions.org/Networks/)

[software phylonet](http://bioinfo.cs.rice.edu/phylonet?destination=node/3)

[software
SplitsTree4](http://tomato.biol.trinity.edu/programs/index.php/SplitsTree4),
also [here](http://www.splitstree.org/)

and lastly a very recent paper to help you get all other references -

[Quartet-based methods to reconstruct phylogenetic
networks](http://www.biomedcentral.com/content/pdf/1752-0509-8-21.pdf)

We will add more on this topic later.

