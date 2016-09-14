---
title: 'MrBayes tgMC3: A Tight GPU Implementation of MrBayes'
tags: []
categories:
- blog
---
Using inherent parallel processing power of hardware is possibly the best way
to handle data deluge in bioinformatics. We are seeing more and more examples
of bioinformatics algorithms being ported to GPUs and other accelerated
hardware. [Here is a good example](http://www.plosone.org/article/info%3Adoi%2
F10.1371%2Fjournal.pone.0060667).
<!--more-->

> MrBayes is model-based phylogenetic inference tool using Bayesian
statistics. However, model-based assessment of phylogenetic trees adds to the
computational burden of tree-searching, and so poses significant computational
challenges. Graphics Processing Units (GPUs) have been proposed as high
performance, low cost acceleration platforms and several parallelized versions
of the Metropolis Coupled Markov Chain Mote Carlo (MC3) algorithm in MrBayes
have been presented that can run on GPUs. However, some bottlenecks decrease
the efficiency of these implementations. To address these bottlenecks, we
propose a tight GPU MC3 (tgMC3) algorithm. tgMC3 implements a different
architecture from the one-to-one acceleration architecture employed in
previously proposed methods. It merges multiply discrete GPU kernels according
to the data dependency and hence decreases the number of kernels launched and
the complexity of data transfer. We implemented tgMC3 and made performance
comparisons with an earlier proposed algorithm, nMC3, and also with MrBayes
MC3 under serial and multiply concurrent CPU processes. All of the methods
were benchmarked on the same computing node from DEGIMA. Experiments indicate
that the tgMC3 method outstrips nMC3 (v1.0) with speedup factors from 2.1 to
2.7. In addition, tgMC3 outperforms the serial MrBayes MC3 by a factor of 6 to
30 when using a single GTX480 card, whereas a speedup factor of around 51 can
be achieved by using two GTX 480 cards on relatively long sequences. Moreover,
tgMC3 was compared with MrBayes accelerated by BEAGLE, and achieved speedup
factors from 3.7 to 5.7. The reported performance improvement of tgMC3 is
significant and appears to scale well with increasing dataset sizes. In
addition, the strategy proposed in tgMC3 could benefit the acceleration of
other Bayesian-based phylogenetic analysis methods using GPUs.

