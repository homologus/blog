---
title: Do Read Errors Matter for Genome Assembly?
tags: []
categories:
- blog
---
We posted about a number of publications from David Tse's group investigating
fundamental limits for assembly algorithms (see
[here](http://www.homolog.us/blogs/blog/2013/01/05/optimal-assembly-for-high-
throughput-shotgun-sequencing/) and
[here](http://www.homolog.us/blogs/blog/2014/09/09/tutorial-on-david-tses-
work-on-dnarna-assembly-presented-at-isit-2014/)). In their
<!--more-->

[latest paper](http://biorxiv.org/content/early/2015/01/26/014399), they look
at how noise in the reads affect those fundamental limits.

> While most current high-throughput DNA sequencing technologies generate
short reads with low error rates, emerging sequencing technologies generate
long reads with high error rates. A basic question of interest is the tradeoff
between read length and error rate in terms of the information needed for the
perfect assembly of the genome. Using an adversarial erasure error model, we
make progress on this problem by establishing a critical read length, as a
function of the genome and the error rate, above which perfect assembly is
guaranteed. For several real genomes, including those from the GAGE dataset,
we verify that this critical read length is not significantly greater than the
read length required for perfect assembly from reads without errors.

It should be obvious that if the reads are 100% noisy, no assembly will be
possible no matter how long the reads are. What is then the 'fundamental
limit' for the error rate in the reads?

The answer depends on the distribution of errors as explained in the paper.

> Our results show that for several actual genomes, if we are in a dense-read
model with reads 20-40% longer than the noiseless requirement `crit(s),
perfect assembly feasibility is robust to erasures at a rate of about 10%.
While this is not as optimistic as the message from [7], we emphasize that we
consider an adversarial error model. When errors instead occur at random
locations, it is natural to expect less stringent requirements.

