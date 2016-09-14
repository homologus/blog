---
title: In Large-scale Biology, Who Has Ownership of the Data?
tags: []
categories:
- rnaseq
---
Our readers may enjoy this story.
<!--more-->

About 2.5 years back, a high-profile group gave us few RNAseq libraries to
analyze. They were analyzing the same libraries by mapping on the genome
(Bowtie/Tophat/Cufflinks), and asked us to check, whether de novo assembly
gave any additional transcript.

You probably remember how transcriptome analysis programs were in late-2010.
Trinity was not published, and Oases was the top dog. However, Velvet itself
was a huge memory hog and Oases needed even more RAM to run. We had to spend
quite a bit of social capital to find an appropriate (high-RAM) computer and
run the assembly. Finally, after begging a friend with high-RAM computer, we
managed to get several Oases runs completed.

We gave the requesting group a set of novel transcripts not identified through
genome alignment. They received a full report, but here is most relevant
paragraph.

>

**Pairwise BLAST Comparison between Velvet and Tophat Sets**

This analysis focuses on 48 hr set. We chose a BLAST cutoff 1e-20.

A. Comparison of 17790 high-FPKM Tophat genes with 38408 Velvet genes

Among 38408 Velvet genes, 28555 (74%) were not present in the Tophat set.

Among 17790 Tophat genes, 1148 (6%) were not present in the Velvet set.

B. Comparison of 78135 Tophat genes with 38408 Velvet genes

Among 38408 Velvet genes, 7269 (19%) were not present in the Tophat set.

Among 78135 Tophat genes, 20643 (26%) were not present in the Velvet set.

The above results are encouraging, because Tophat-Cufflink utilized the
already assembled genome, whereas Velvet did not have such an advantage. Still
Velvet assembled almost all (94%) highly expressed genes identified by Tophat.

Shock and horror - those biologists told us that they are already in the
process of writing a paper with 'conclusion' that de novo assembly would give
nothing new, but

asked us to do the analysis so that they could claim in the paper that they
did run the analysis. We were not ready to go with that, and then came the
next set of surprises. Those eminent biologists told us that we must have done
something wrong in the analysis, because, well, they 'concluded' in their
soon-to-be-submitted paper that assembly approach would not give anything new.
To be honest, they did try to give few explanations on why de novo assembly
would do things wrong.

(i) "Who knows what pieces those assembly programs are connecting" [We had to
do more analysis of assembled fragments to show that they usually fell on the
same scaffold, which is highly unlikely in case of random junctions.]

(ii) "Maybe those extra pieces were all UTRs" [We found that about 1/3rd to
1/2 of potentially novel transcripts were reasonably close to other genes to
be classified as UTRs].

However, the general process of exchange was utterly frustrating, because
those guys made up their mind and were trying to find some way to show that
Velvet was wrong. Also, they kept making suggestions that they did not need to
back their assertions with proof, because they were well-known biologists. So,
we offered - "Why not you present your results in the upcoming conference, and
we present ours? Then we will let the general scientific community decide who
was correct."

At that point, they pulled out their final trump card.

"We are the owners of primary data. You cannot present anything without our
permission."

What is the opinion of our readers? Who is allowed to present analysis of
large-scale biological data in similar situations?

