---
title: "'Network Nonsense' at Lior Pachter's Blog Escalates"
tags: []
categories:
- blog
---
**Biological Context - Yeast Protein Interaction Network**
<!--more-->

In 2002, two back-to-back papers got published in Nature, giving researchers a
large treasure-trove of yeast 2-hybrid protein interaction data.

[Gavin, A. C., Bosche, M., Krause, R., Grandi, P., Marzioch, M., Bauer, A.,
Schultz, J., Rick, J. M., Michon, A. M., Cruciat, C. M., et al. (2002) Nature
415,141147.](http://www.ncbi.nlm.nih.gov/pubmed/11805826)

[Ho, Y., Gruhler, A., Heilbut, A., Bader, G. D., Moore, L., Adams, S. L.,
Millar, A., Taylor, P., Bennett, K., Boutilier, K., et al. (2002) Nature 415,
180183.](http://www.ncbi.nlm.nih.gov/pubmed/11805837)

Biologists got very excited, because they could search the databases to find
interactions of any protein and make hypothesis about its biological role in
the cell. Around that time, about 30-40% of yeast proteins could not be
annotated by straightforward methods (i.e. alignment+orthology) and that
bothered scientists quite a bit. What roles did the 'unknownome' play?

Biologists faced one problem however. The interaction data were quite noisy
and led biologists into all directions, if they wanted to explore the
interactions of any single protein. Lab experiments cost time and money, and
imagine the life of a post-doc, who made three wrong hypotheses from three
'wrong' interactions and spent his life chasing ghosts !! Computational
biologists of all creed and color jumped in, because the database was fresh
and the problem of noise reduction has clear biological relevance. I was at
NASA Ames that time and along with Shoudan Liang (an extremely smart ex-
physicist) and Jason Chin (who possibly does not need introduction to our
readers), we decided to apply all kinds of graph theoretic approaches to the
interaction data to see what we could get. As far as I can tell, there are
only three possibilities, and all others reduced to those in one way or other.

**Method 1. Using Fat-tailed Distribution**

In 2003, I used a probabilistic method to score every protein pair and then
clustered those pairs into larger group.

> To compute the P value, we count the number of distinct ways in which two
proteins with n1 and n2 interaction partners have m in common. We divide the
whole set of partners of the two proteins into three nonoverlapping groups:

We later came to find that [Goldberg and Roth from Harvard used the same
formula](http://www.pnas.org/content/100/8/4372.full.pdf), but I did something
bold that was unheard of among computational biologists in those days. I
manually checked the interactions of all unknown proteins with high ranks in
our method, predicted the functions and added those functions at the SGD
(Stanford yeast genome database) as new annotations. The reason was that our
method worked extremely well for proteins with known functions, and therefore
it made sense to guide experimentalists with the predictions. The paper is
linked below, but real meat is in [supplementary tables 5 and 6](http://www.pn
as.org/content/suppl/2003/10/08/2132527100.DC1/2527Table5.pdf), which took me
more than two months to prepare.

[Predicting protein functions from redundancies in large-scale protein
interaction networks](http://www.pnas.org/content/100/22/12579.full.pdf)

**Method 2. Percolation**

In 2003, Jason Chin investigated the protein interaction data using
percolation method and showed that the graph was clearly non-random with
essential genes sitting at the core. It was a very profound observation, but
we did not know how to convey the results in biological language. Even the
computational biologists of that day (mostly database hacks or computer-
science professors) had problem understanding percolation. The paper is linked
below.

[Global snapshot of a protein interaction networka percolation based approach]
(http://bioinformatics.oxfordjournals.org/content/19/18/2413.full.pdf)

I found his observation profound for another reason. When I compared the high-
scoring nodes from his network with aging-related genes, it appeared that most
of those high-scoring genes were also 'longevity genes'. However, to turn the
above paper into a biological one, I had to motivate some biologists to sit in
front of a microscore and check yeast divisions over hours. Sadly, I could not
find any such biologist, who could also appreciate percolation theory to
understand what he was doing.

Our secret of long-life had to wait for another day !!

Edit.

I asked Jason Chin to review the above text and he added following comment.

> I think computer scientists should have no problem to understand percolation
(it is just like the power of adjacent matrix to some degree.) I guess what
most of them dont get is the qausi-phase-transistion. A different community
understands that better. There are many nice papers on applying the phase-
transistion idea for the k-SAT problem. (In general, very rigorous
mathematical work.)

One problem in quantitive biology is that some people are yet to understand
the value of rigorous work like mathematicians and know how to make good
approximations and justify them like physicists.

Also the quasi-phase-transition peak gives a natural choice of the percolation
parameter. Not sure how that relates to the parameter in Kellis paper. I have
not read the paper so I have no clue at all.

**Method 3. Finding cliques**

Around the same time, Shoudan looked into the third approach, namely finding
cliques of various sizes/fuzziness and checking whether they were present in
the network in statistically significant number. One thing about cliques -
computer scientists understand them and love them. The second thing about
cliques - they were lousy methods to understand yeast protein interaction
network based on our experience.

Finding cliques is not easy and Shoudan made great algorithmic progress. Since
we could not apply it in protein-interaction network or rather the method 1
worked spectacularly well compared to this one, we decided to apply his
approach to DNA motif sequences and send a paper to CSB conference.

[cWINNOWER ALGORITHM FOR FINDING FUZZY DNA
MOTIFS](http://www.worldscientific.com/doi/abs/10.1142/S0219720004000466)

> The cWINNOWER algorithm detects fuzzy motifs in DNA sequences rich in
proteinbinding signals. A signal is defined as any short nucleotide pattern
having up to d mutations differing from a motif of length l. The algorithm
finds such motifs if a clique consisting of a suffciently large number of
mutated copies of the motif (i.e., the signals) is present in the DNA
sequence. The cWINNOWER algorithm substantially improves the sensitivity of
the winnower method of Pevzner and Sze by imposing a consensus constraint,
enabling it to detect much weaker signals. We studied the minimum detectable
clique size qc as a function of sequence length N for random sequences. We
found that qc increases linearly with N for a fast version of the algorithm
based on counting threemember sub-cliques. Imposing consensus constraints
reduces qc by a factor of three in this case, which makes the algorithm
dramatically more sensitive. Our most sensitive algorithm, which counts four-
member sub-cliques, needs a minimum of only 13 signals to detect motifs in a
sequence of length N=12,000 for (l,d)=(15,4).

\-----------------------------------------------------------------------------
----------------------------
----------------------------
------------------
