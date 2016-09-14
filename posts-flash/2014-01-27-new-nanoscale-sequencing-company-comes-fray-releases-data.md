---
title: A New Nanoscale Sequencing Company Comes into Fray and Releases Data !!
tags: []
categories:
- blog
---
Expecting a new sequencing company to release raw data along with big claims
was not unusual in the Mesozoic era of next-gen genomics, but then Oxford
Nanopore evolved into existence. Thankfully, other nanopore companies are not
following the same marketing model. A new nanoscale company named Quantum
Biosystems went public with their instruments today along with a data release
page.
<!--more-->

![Capture](http://www.homolog.us/blogs/wp-
content/uploads/2014/01/Capture3-300x72.png)

This Japanese company likely follows the method published in Nature Scientific
Reports in 2012, where its authors demonstrated the sequencing of let-7
microRNA molecule using their technology.

![](http://www.nature.com/srep/2012/120710/srep00501/images_article/srep00501-
f4.jpg)

[Single-Molecule Electrical Random Resequencing of DNA and
RNA](http://www.nature.com/srep/2012/120710/srep00501/full/srep00501.html)

> Two paradigm shifts in DNA sequencing technologiesfrom bulk to single
molecules and from optical to electrical detectionare expected to realize
label-free, low-cost DNA sequencing that does not require PCR amplification.
It will lead to development of high-throughput third-generation sequencing
technologies for personalized medicine. Although nanopore devices have been
proposed as third-generation DNA-sequencing devices, a significant milestone
in these technologies has been attained by demonstrating a novel technique for
resequencing DNA using electrical signals. Here we report single-molecule
electrical resequencing of DNA and RNA using a hybrid method of identifying
single-base molecules via tunneling currents and random sequencing. Our method
reads sequences of nine types of DNA oligomers. The complete sequence of
5?-UGAGGUA-3? from the let-7 microRNA family was also identified by creating a
composite of overlapping fragment sequences, which was randomly determined
using tunneling current conducted by single-base molecules as they passed
between a pair of nanoelectrodes.

The [newly released
data](http://www.quantumbiosystems.com/datalist/index.html?lang=en) also
includes 2001 signal points from let-7 along with a pdf file with description
of base-calling and other methods. For base-calling, the company uses hidden
Markov model with transition probability from one nucleotide to the next. We
wonder, whether the [BlindCall approach discussed last
week](http://www.homolog.us/blogs/blog/2014/01/23/blindcall-ultra-fast-base-
calling-algorithm-using-blind-deconvolution/) would be appropriate for their
technology. That leads to the more important question of whether de-
multiplexed single electrical signal can achieve the same error rate as four-
color signals from competing technologies. Hopefully, the company will share
more data on longer DNA molecules for researchers to play with.

