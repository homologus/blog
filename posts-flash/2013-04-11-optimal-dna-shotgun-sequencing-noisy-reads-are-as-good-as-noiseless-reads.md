---
title: 'Optimal DNA Shotgun Sequencing: Noisy Reads are as Good as Noiseless Reads'
tags: []
categories:
- blog
---
[This arxiv paper](http://arxiv.org/pdf/1304.2798v1.pdf) is making the rounds
in twitter today.
<!--more-->

> We establish the fundamental limits of DNA shotgun sequencing under noisy
reads. We show a surprising result: for the i.i.d. DNA model, noisy reads are
as good as noiseless reads, provided that the noise level is below a certain
threshold which can be surprisingly high. As an example, for a uniformly
distributed DNA sequence and a symmetric substitution noisy read channel, the
threshold is as high as 19%.

It uses concepts from information theories to define the limitations of
sequencing technologies. We covered some of the basic concepts [in a blog post
more than a year back](http://arxiv.org/pdf/1304.2798v1.pdf). Basic idea is
this. Bioinformaticians tend to add too much premium to perfect sequencing
than slightly imperfect sequencing, but that premium could be due to
limitations of existing algorithms than the sequencing technology. In digital
and analog communication, data gets transferred from one point to another,
even though the channels have some degree of noise. In fact, when signals are
transmitted from Mars to Earth, the channel is extremely noise, yet the the
original transmitted images can be reconstructed with high degree of accuracy.

The above Berkeley group has been doing very interesting mathematical work on
sequencing, and we covered their earlier paper few months back. Many readers
made insightful comments on [Optimal Assembly for High Throughput Shotgun
Sequencing](http://www.homolog.us/blogs/2013/01/05/optimal-assembly-for-high-
throughput-shotgun-sequencing/)

Going through the current paper, here are the key concepts. In noiseless
systems,

> The optimal assembly algorithm which achieves the fundamental limit in the
above setting is the greedy algorithm.

What happens in noisy sequencer?

> The modi?cation of the greedy algorithm is only one approach to deal with
noise. But are there better approaches? What, in fact, is the fundamental
limit on the system performance under noisy reads? We show a surprising result
in this paper: provided that the noise level is below a certain threshold,
noise has no impact on the asymptotic performance

What it means for assembly.

> The scheme we propose to achieve the fundamental limit under noisy reads has
two stages: an error-correction phase, which aligns reads from the same region
of the DNA and averages across them to produce cleaner reads, followed by an
assembly phase, applying the greedy algorithm with approximate match to the
cleaner reads. Provided that the noise level satis?es condition (1) to allow
accurate read alignment, the noise level of the reads can be driven to be
vanishingly small after the error-correction phase. Since it was shown in [7]
that the performance of the greedy algorithm is continuous in the noise level,
this implies noiseless performance can be achieved asymptotically.

In the assembly literature, there are two approaches to deal with the noise in
the reads. In the ?rst approach, error-correction is performed jointly with
assembly such as Velvet [10] and ABySS [4] which are based on de Bruijn graph.
In the second approach, error correction is performed ?rst, followed by an
assembly algorithm which assumes the reads are essentially clean. Examples of
the algorithms are SHREC [3], Reptile [9], and Quake [5]. The latter is a
separation approach, which is conceptually simpler. What we show in this paper
is that, at least for the simple model considered here, the separation
approach is in fact information-theoretically optimal, up to a certain
threshold on the noise level.

Bottom line - just like we saw in case of internet search, once again
electrical engineers win over computer scientists :)

\--------------------------------

Our friend Dr. Chen-Shan Chin provides some insight on the next difficult
problem in assembly -

>

Our advance (at both intellectual level and practical level) is more on new
algorithms to handle indel errors better. (In communication theory, this is
related to "insertion-deletion channel" problem. There are still a lot of open
questions about it.)

