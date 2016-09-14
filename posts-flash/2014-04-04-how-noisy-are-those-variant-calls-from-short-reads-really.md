---
title: How Noisy Are Those Variant Calls from Short Reads Really?
tags: []
categories:
- blog
---
In "[End of Short-Read Era? (Part
I)](http://www.homolog.us/blogs/blog/2013/09/21/end-illumina-era/)", we argued
that clean short reads were noisy for being short and that 'noise' often gets
realized at the next level of analysis. For example, the genome assembly may
have too many holes or too many genes may appear to go through accelerated
evolution. **In a new preprint uploaded at arxiv**, Heng Li estimated the
degree of error in case of variant calling.
<!--more-->

[Towards Better Understanding of Artifacts in Variant Calling from High-
Coverage Samples](http://arxiv.org/pdf/1404.0929v1.pdf)

>

Whole-genome high-coverage sequencing has been widely used for personal and
cancer genomics as well as in various research areas. However, in the lack of
an unbiased whole-genome truth set, the global error rate of variant calls and
the leading causal artifacts still remain unclear even given the great efforts
in the evaluation of variant calling methods.

Results: We made ten SNP and INDEL call sets with two read mappers and ?ve
variant callers, both on a haploid human genome and a diploid genome at a
similar coverage. By investigating false heterozygous calls in the haploid
genome, we identi?ed the erroneous realignment in low-complexity regions and
the incomplete reference genome with respect to the sample as the two major
sources of errors, which press for continued improvements in these two areas.
We estimated that the error rate of raw genotype calls is as high as 1 in
1015kb, but the error rate of post-?ltered calls is reduced to 1 in 100200kb
without signi?cant compromise on the sensitivity.

Availability: BWA-MEM alignment: http://bit.ly/1g8XqRt

Scripts: https://github.com/lh3/varcmp

Additional data: http://?gshare.com/account/projects/1013

The availability of a haploid cell-line allowed him to do this analysis. We
could not open the scripts or additional data link, but those were not needed
to evaluate this well-written and informative paper. While reading it, we kind
of got the sense that **variant calling through alignment still remains a dark
art**. Here are two example -

1\.

> Although most callers deploy advanced models for homopolymer INDELs, they
are calling vastly different number of 1bp heterozygous INDELs. It is still
not clear to us that we can model PCR errors well. Maybe the most effective
solution is to avoid PCR in sample preparation.

2\.

>

Without the thorough understanding of the very details of the realignment
process, we are unable to explain why the callers fail even on some obvious
cases.

In the process of manual review, we found local assembly with fermi is
frequently more effective than the INDEL callers, which may be due to the
independence of the reference sequence, the requirement of long-range
consistency and the more powerful topology based error cleaning (Zerbino and
Birney, 2008). Some dif?cult errors such as Figure 4 are trivial to resolve
with local assembly.

Therefore, it may be considered good news that **he discovered a new dark art
through his work** and consultation with Peter Sudmant -

> When we called SNPs and INDELs from CHM1, we were surprised to ?nd 10% of
raw variant calls were heterozygotes. Honestly, our immediate reaction was
that CHM1 was not truly haploid. However, after careful analysis, we have
convinced ourselves that the heterozygosity of CHM1 should be of an order of
magnitude lower than the raw error rate of variant calling. The vast majority
of heterozygotes are calling errors. In the raw call set, we usually see an
error per 1015kb.

It was also to our surprise that the low-complexity ?lter is the most
effective against false heterozygotes, especially short INDELs. Without the
suggestion from Peter Sudmant (personal communication), we would not have
tried this ?lter in the ?rst place. Realignment in LCRs still needs
improvements in addition to the existing efforts in this direction (Homer and
Nelson, 2010; Li, 2011a; Albers et al., 2011).

For those looking for what could be an useful follow-up of Heng Li's work,
**PacBio has also released a re-sequencing library of the same haploid human
cell line** \-

> As we were writing up this work, Paci?c Biosciences released deep
resequencing data for the CHM1 cell line. It could be used to isolate errors
caused by the Illumina sample preparation and sequencing. However, mapping and
variant calling from PacBio human data is still in the early phase. We decided
to leave out the comparison to the PacBio data for now.

