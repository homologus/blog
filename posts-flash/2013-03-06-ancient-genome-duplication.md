---
title: Ancient Genome Duplication
tags: []
categories:
- blog
---
The topic of genome duplication gets revisited often in genome analysis and
[Lamprey genome
paper](http://www.nature.com/ng/journal/vaop/ncurrent/full/ng.2568.html) is
the most recent example. We are going through past literature and decided to
keep notes here for anyone else interested.
<!--more-->

**Biological Implication**

In 1967, Ohno wrote in his article titled ["Evolution From Fish to Mammals by
Gene Duplication"](http://onlinelibrary.wiley.com/doi/10.1111/j.1601-5223.1968
.tb02169.x/abstract) \-

> While speciation from an immediate common ancestor can be explained by
allelic mutations at already existing gene loci, when evolution of the sub-
phylum _Vertebrata_ is considered _in toto_, allelic mutations are no longer
sufficent to account for all the changes that have taken place during the past
300 million years. Gene duplication now emerges as the prime factor of
evolution. It is becoming increasingly clear that in higher organisms such as
mammals, one particular function is more often assigned to a group of several
gene loci rather than to a single gene locus. Products of these several genes
which arose by duplication from an ancestral gene perform the same function
but in slightly different ways. These slight differences are exploited during
ontogeny. Each somatic cell type at a given stage of development
preferentially activates a few from the group of duplicated genes which fit
the particular need of that cell type.

With passage of time, various changes take place in the the genome.

_Random mutation of nucleotides_

At the lowest timescale, various nucleotides in the genome get randomly
mutated. Some As turn into Gs, Cs or Ts, some Cs turn into As and so on.
Depending on where the mutation occurs, this change gives offspring slightly
different property. At times, random mutations within non-essential genes may
turn them into pseudo-genes.

_Insertion and deletion of nucleotides_

At the next higher time scale, nucleotides get randomly inserted or deleted
from here and there in the genome.

_Insertion and deletion of genes_

From time to time, large chunks of nucleotides get duplicated or deleted too,
and some of those chunks may have functional elements such as protein-coding
genes. Over time, the newly created proteins may accept new functions.

_Rearrangement of the genome_

Rarely chunks of genome break and join other parts of the genome. Half of
chromosome 7 may merges with 1/3rd of chromosome 2 to create a new chromosome.
If the break point has two neighboring essential genes, who function through
coexpression from a single promoter, splitting of chromosome can make them
non-functional. Selection pressure would demand those two genes to stick
together through all trials and tribulations.

_Genome duplication_

Genome duplication is the rarest of all possible genome rearrangements. In
this case, the entire genome of an organism duplicates to create two copies of
every single gene. Eventually, one copy of each gene continues to do what it
was doing before, while the other one may get recruited to perform completely
new tasks, or may get removed from the genome.

Ohno proposed that whole genome duplication was an important evolutionary
mechanism to get so much diversity in animal kingdom, but confirmation of its
validity had to wait for another ~30 years.

**Bioinformatic Challenges in Finding Genome Duplication**

Let us say someone analyzes a genome and tells you that it went through whole
genome duplication two times in the past. Why should we need to take such
analysis with a grain of salt?

_Quality of genome assembly_

We know that most published genomes are not fully assembled chromosomes, but
rather a large group of scaffolds waiting to be turned into chromosomes some
day in future. Few genes may be present twice or more due to inaccuracy in
assembly. For example, polymorphic regions are very difficult to assemble.
What if two copies of a gene are merely polymorphic versions of the same
genomic region?

_Gene Duplication_

Even if the entire genome got duplicated in the past, many genes disappear
after such duplication event. Let us say genes 1, 2, 3, 4, 5 and 6 get
duplicated into genes (1a, 2a, 3a, 4a, 5a, 6a) and (1b, 2b, 3b, 4b, 5b, 6b).
Then 1a, 2b, 3b and 6b disappears and we are left with (1b, 2a, 3a, 4a, 4b,
5a, 5b and 6a). How do we know that 4a and 4b or 5a and 5b came from whole
genome duplication, and not merely duplication of 5 and 6?

A good bioinformatic analysis should address those issues.

**Literature**

It is no surprise that the first genome duplication paper in eukaryote came
obviously after first eukaryotic genome was published ([abstract](http://www.n
ature.com/nature/journal/v387/n6634/full/387708a0.html), [pdf](http://charlott
e.ucsd.edu/classes/wi05/cse206b/pub/wolfe_Nature_1997.pdf)).

**Molecular Evidence for an Ancient Duplication of the Entire Yeast Genome - 

Kenneth H. Wolfe & Denis C. Shields**

> Gene duplication is an important source of evolutionary novelty. Most
duplications are of just a single gene, but Ohno proposed that whole-genome
duplication (polyploidy) is an important evolutionary mechanism. Many
duplicate genes have been found in Saccharomyces cerevisiae, and these often
seem to be phenotypically redundant. Here we show that the arrangement of
duplicated genes in the S. cerevisiae genome is consistent with Ohnos
hypothesis. We propose a model in which this species is a degenerate
tetraploid resulting from a whole-genome duplication that occurred after the
divergence of Saccharomyces from Kluyveromyces. Only a small fraction of the
genes were subsequently retained in duplicate (most were deleted), and gene
order was rearranged by many reciprocal translocations between chromosomes.
Protein pairs derived from this duplication event make up 13% of all yeast
proteins, and include pairs of transcription

factors, protein kinases, myosins, cyclins and pheromones. Tetraploidy may
have facilitated the evolution of anaerobic fermentation in Saccharomyces.

My bioinformatician colleagues and I used to discuss the above paper in 2001,
and most were distrustful of the results. Why? It was because of the
bioinformatics challenges mentioned above. Wolfe and Shields did not have to
deal with incomplete chromosomes, but they had to address the question of gene
deletion after whole genome duplication versus isolated gene duplication. This
paragraph from methods section was what we used to debate about -

> **Statistical analysis.** Chi-square tests (data not shown) indicate that
duplicated genes in yeast are distributed in a highly non-random manner with
regard to both the order in which homologous genes occur on pairs of
chromosomes and the transcriptional orientations of those genes. A
simultaneous origin of duplicate regions, as opposed to 55 independent
duplications, is supported by a chi-square test on block orientations and by
the lack of triplicated regions. The Poisson expectation if blocks were
duplicated sequentially is for approximately 40 duplicated blocks, and 7
blocks that are replicated more than once (mainly triplicated). There is only
one possible candidate for a triplicated region...

Another reason we used to discuss the paper was because rarely pure
bioinformatics paper got accepted in Nature ([here was
another](http://www.nature.com/nature/journal/v406/n6798/abs/406916a0.html)).
Poor bioinformaticians like us did not have money to do experiments, and we
could not get that money without papers in Science and Nature. Heard the
problem before?

Next major paper on the same topic came about seven years later. It was not a
completely bioinformatics paper, but it was also memorable for being the first
genome paper with less than 400 authors :). Personally I remember the paper
well, because I worked on their sequence data right after the paper came out.
That was when I learned for the first time that genomes, even if published,
were rarely nice sets of complete chromosomes.

[Proof and Evolutionary Analysis of Ancient Genome Duplication in the Yeast
Saccharomyces cerevisiae - Kellis, Birren and Lander](http://www.ualberta.ca/~
allisonj/Gen302%20Readings/22%20Genome%20duplication%20history%20/KellisLander
%20-%20Proof%20and%20evolutionary%20analysis%20of%20ancient%20genome%20duplica
tion%20in%20the%20yeast%20Saccharomyces%20cerevisiae.pdf)

>

Whole-genome duplication followed by massive gene loss and specialization has
long been postulated as a powerful mechanism of evolutionary innovation.
Recently, it has become possible to test this notion by searching complete
genome sequence for signs of ancient duplication. Here, we show that the yeast
Saccharomyces cerevisiae arose from ancient whole-genome duplication, by
sequencing and analysing Kluyveromyces waltii, a related yeast species that
diverged before the duplication. The two genomes are related by a 1:2 mapping,
with each region of K. waltii corresponding to two regions of S. cerevisiae,
as expected for whole-genome duplication. This resolves the long-standing
controversy on the ancestry of the yeast genome, and makes it possible to
study the fate of duplicated genes directly. Strikingly, 95% of cases of
accelerated evolution involve only one member of a gene pair, providing strong
support for a speci?c model of evolution, and allowing us to distinguish
ancestral and derived functions.

Interestingly, Manolis Kellis' recent ENCODE paper ([Ward and
Kellis](http://www.sciencemag.org/content/337/6102/1675.abstract)) was the
only one mentioned by Dan Graur to be one consistent with evolutionary theory.

> Our results suggest continued turnover in regulatory regions, with at least
an additional 4% of the human genome subject to lineage-specific constraint.

**Literature Review in Fishes**

Next, we will go through a set of papers on ancient genome duplication in
fishes ending with the Lamprey paper. The topic of genome duplication in
fishes has been explored extensively by Axel Meyer, Yves Van de Peer, John S.
Taylor and  Ingo Braasch. Their first paper on this topic [appeared
in 2001](http://www.ncbi.nlm.nih.gov/pmc/articles/PMC1088543/)
([pdf](http://www.ncbi.nlm.nih.gov/pmc/articles/PMC1088543/pdf/TB011661.pdf)).
The main claim was that vertebrates went through ancient genome duplication
twice in the past, but teleost fishes had an extra round of genome
duplication.

>

**Comparative genomics provides evidence for an ancient genome duplication event in fish**

There are approximately 25000 species in the division Teleostei and most are
believed to have arisen during a relatively short period of time ca. 200 Myr
ago. The discovery of 'extra' Hox gene clusters in zebrafish (Danio rerio),
medaka (Oryzias latipes), and pufferfish (Fugu rubripes), has led to the
hypothesis that genome duplication provided the genetic raw material necessary
for the teleost radiation. We identified 27 groups of orthologous genes which
included one gene from man, mouse and chicken, one or two genes from
tetraploid Xenopus and two genes from zebrafish. A genome duplication in the
ancestor of teleost fishes is the most parsimonious explanation for the
observations that for 15 of these genes, the two zebrafish orthologues are
sister sequences in phylogenies that otherwise match the expected organismal
tree, the zebrafish gene pairs appear to have been formed at approximately the
same time, and are unlinked. Phylogenies of nine genes differ a little from
the tree predicted by the fish-specific genome duplication hypothesis: one
tree shows a sister sequence relationship for the zebrafish genes but differs
slightly from the expected organismal tree and in eight trees, one zebrafish
gene is the sister sequence to a clade which includes the second zebrafish
gene and orthologues from Xenopus, chicken, mouse and man. For these nine gene
trees, deviations from the predictions of the fish-specific genome duplication
hypothesis are poorly supported. The two zebrafish orthologues for each of the
three remaining genes are tightly linked and are, therefore, unlikely to have
been formed during a genome duplication event. We estimated that the unlinked
duplicated zebrafish genes are between 300 and 450 Myr. Thus, genome
duplication could have provided the genetic raw material for teleost
radiation. Alternatively, the loss of different duplicates in different
populations (i.e. 'divergent resolution') may have promoted speciation in
ancient teleost populations.

Other related papers -

[Genome Duplication, a Trait Shared by 22,000 Species of Ray-Finned Fish
(2003)](http://genome.cshlp.org/content/13/3/382.full)

[Major events in the genome evolution of vertebrates: Paranome age and size
differ considerably between ray-finned fishes and land vertebrates
(2004)](http://www.pnas.org/content/101/6/1638.long) (h/t: Vandepoele lab
?@plaza_genomics with note - "How a phylogenomics approach can partially deal
with bad assemblies")

[Phylogenetic Timing of the Fish-Specific Genome Duplication Correlates with
the Diversification of Teleost Fish
(2004)](http://link.springer.com/article/10.1007%2Fs00239-004-2613-z?LI=true)

[Gene Loss and Evolutionary Rates Following Whole-Genome Duplication in
Teleost Fishes (2006)](http://mbe.oxfordjournals.org/content/23/9/1808.short)

[Duplicated Gene Evolution Following Whole-Genome Duplication in Teleost
Fish](http://cdn.intechopen.com/pdfs/21907/InTech-Duplicated_gene_evolution_fo
llowing_whole_genome_duplication_in_teleost_fish.pdf)

Reader Josesh Normal kindly suggested few other very relevant papers in the
comment section. We are including recent ones here, but one classic text he
mentioned is also valuable.

[Genome duplication in the teleost fish Tetraodon nigroviridis reveals the
early vertebrate proto-karyotype](http://www.nature.com/nature/journal/v431/n7
011/abs/nature03025.html)

[The medaka draft genome and insights into vertebrate genome evolution](http:/
/www.nature.com/nature/journal/v447/n7145/full/nature05846.html)

[Reconstruction of the vertebrate ancestral genome reveals dynamic genome
reorganization in early
vertebrates](http://www.ncbi.nlm.nih.gov/pmc/articles/PMC1950894/)

**Importance of Lamprey Genome**

For yeast, the ancient genome duplication was suggested to be sometime after
divergence of Saccharomyces from Kluyveromyces, as suggested by Wolfe and
Shields through statistical analysis. Many researchers did not want to believe
that analysis, but Kellis' paper confirmed it empirically by sequencing
Kluyveromyces yeast. Vertebrates went through two such rounds of genome
duplication (2R) and teleost fish went through another extra round (3R). When
exactly those duplications happened is an important question that Lamprey
paper set out to answer. Their answer -

> Analyses of the assembly indicate that two whole-genome duplications likely
occurred before the divergence of ancestral lamprey and gnathostome lineages.

but that short sentence twitterifies very hard work by a team of 59
scientists. We will cover those details in a separate commentary.

