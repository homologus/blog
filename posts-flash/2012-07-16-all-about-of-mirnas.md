---
title: All About miRNAs
tags: []
categories:
- blog
---
We have a small treat for those working on miRNAs.
<!--more-->

Readers are likely wondering what we may have to add on miRNAs at this late
hour given that thousands of papers have already been published on those tiny
regulators. However, if you closely follow the developments in the field, you
will notice that they went through three revolutionary phases.

In the first phase, miRNAs were completely new and researchers were busy
figuring out what exactly they do and the molecular mechanism through which
they operate. Quite a bit was learned about pri-miRNA, the precursor hairpin
structure, and the mature 22-mer that worked as regulators of protein-coding
genes. Enzymes such as Dicer and Drosha were discovered. Bioinformaticians got
busy writing codes to predict hairpin folding and target-prediction.

In the meanwhile, many new eukaryotic genomes were sequenced and researchers
started asking question about whether miRNAs existed in different branches of
the tree of life. 'Are they present in yeast?' Do all insect genomes have
miRNAs?' '[Does red algae _Ectocarpus_ have
miRNA?](http://www.ncbi.nlm.nih.gov/pubmed/20520714)'

The most surprising discovery of this second phase, in our opinion, was the
discovery of miRNAs in viral genome. From ScienceDaily (June 12, 2006) -

> Researchers at the University of Pennsylvania School of Medicine have
discovered part of the reason why cold sores, caused by a herpes virus, come
back again and again. The new study, published online last month in Nature,
points to a small RNA molecule, called a microRNA (miRNA) as the culprit that
keeps the latent virus-infected cell alive. These findings could one day lead
to a new way to fight the virus and offers the first target for intervention
in the latent infection.

[Here](http://www.pnas.org/content/109/8/3077) is a more recent article on
viral miRNAs, if you like to know what has been learned about them since 2006.

At present, the miRNA field is in its third phase of growth and next-gen
sequencing is the main driver. Today, the presence of miRNAs in genomes is as
accepted as protein-coding genes, and the hairpin-folding mechanism is as
well-known among biologists as genes translating into proteins guided by
genetic code. However, the miRNAs are not just miRNAs any more, but known more
as miR-20, miR-101, etc. - each with its own idiosyncrasy. What those
different miRNAs do is the most important question keeping biologists awake.

Finding evolutionary relationship is one important tool in exploring different
miRNA classes, because mature miRNAs are known to preserve their sequences
over long evolutionary distance. This is where high-throughput sequencing has
become very helpful. In the earlier days, researchers used to analyze
individual genomes to find the presence of miRNAs in various organisms. Today,
a researcher can potentially sequence miRNA libraries from many organisms
together using high-throughput sequencing technology. Length of reads is not
of big concern for those tiny RNAs.

Last week we were working on one such library, and short-listed a set of
interesting miRNAs. Next we dived into [miRbase](http://www.mirbase.org/) to
learn as much about them as possible. Here are the typical questions we asked
for each miRNA (let us take miR-17 as an example):

(i) In which organisms is miR-17 present?

(ii) What is the evolutionary relationship between those organisms? For
example, if a family of miRNAs is previously found only in worms and insects,
and we find it in a bird, that is a new finding regarding the miRNA family.

(iii) How do mature miRNAs miR-17s from those organisms align?

(iv) Which genes are the neighbors of miR-17 in those various genomes? Also,
we like to see miR-17 in the genomic context in genome browsers of those
organisms. We suspect many miRNAs also preserve genomic synteny structure over
long evolutionary distance (could anyone please refer to a paper on the
topic)?

After jumping around from database to database, we got frustrated and decided
to build the above questions [into our search
tool](http://homolog.us/CI/index.php/search). The infrastructure is ready, and
you can see miR-17 here. All fields are not complete yet, but you can see
where it is going. The organisms are all grouped together according to their
taxonomies.

![](http://www.homolog.us/blogs/wp-
content/uploads/2012/07/Capture3-300x135.jpg)

The biggest challenge in developing something for the web is to make the codes
flexible enough to incorporate changes in available data. For example, if we
hand-curate the organisms and tomorrow miRBase incorporates data from 15 new
organisms, we will need to get back to the drawing board. Our design is
flexible so that new data can be easily incorporated. All that needs to be
done is to populate the databases with latest information regarding various
fields of the table (including neighboring genes).

We will keep you posted on further developments of the miRNA tool. Any helpful
suggestion is welcome.

