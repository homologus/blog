---
title: The Mapping God Speaketh
tags: []
categories:
- blog
---
Readers may take a look at this informative Biostar commentary from Heng Li on
comparison of five short-read aligners -
<!--more-->

[Tutorial: For short reads, which aligners find all hits given certain edit
distance threshold?](http://www.biostars.org/p/63659/)

The following snippets from his conclusion presents the state of the art of
various mapping tools, but readers will find lot more in the linked
discussion.

>

EDIT2: Conclusions (so far):

With the suggestions from nkrumm and David, we can say that bwa, gem, mrfast,
segemehl and RazerS3 probably guarantee to find hits within certain hamming
distance threshold. These mappers all support gapped alignment, but whether
they guarantee to find all gapped hits given an edit-distance threshold has
not been concluded. Neither bowtie nor bowtie2 guarantees to find all hits.

For practical uses, bwa's try-and-reject strategy is probably faster for <32bp
sequences. MrFast, gem and razers3 all use the pigeon hole approach. They
should be faster for longer reads (e.g. 36-100bp). BWA and gem index the
genome. They have fixed memory footprint and is easier to run (you do not need
to split the read file when it is too large), and also run much faster if you
only have a few to a couple of thousands of reads at hand. I would recommend
them in general.

All that being said, for 100bp reads, finding all hits given a certain edit-
distance threshold is not sufficient. We would like to see if alignments
containing one reasonably long gap (say 7bp insertion) and to rank the hits by
affine gap penalty instead of by edit distance. In computer science, edit
distance is popular as it is clearly defined and many efficient algorithm
exist to find matches. However, affine gap penalty is of more
biological/evolutionary meaning.

\----------------

The presentation seemed to have annoyed one Biostar reader, who found the
author too biased toward BWA and left in disgust.

> But still, I do not like your agressive style. Who are you? The mapping god?
You judge other tools in a very unkind way. Yeah, bwa rocks. I think we all
see that now (with hundreds of special parameters at least). I do not like
these fights. Have fun.

Life isn't fair, we guess !!

