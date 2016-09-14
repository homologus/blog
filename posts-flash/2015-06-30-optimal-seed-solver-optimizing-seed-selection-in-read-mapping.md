---
title: 'Optimal Seed Solver: Optimizing Seed Selection in Read Mapping'
tags: []
categories:
- blog
---
[Link](http://arxiv.org/abs/1506.08235)
<!--more-->

**The core algorithm**

> A naive brute-force solution to find the optimal seeds of a read would be
systematically iterating through all possible combinations of seeds. We start
with selecting the first seed by instantiating all possible positions and
lengths of the seed. On top of each position and length of the first seed, we
instantiate all possible positions and lengths of the second seed that is
sampled after (to the right-hand side of) the first seed.We repeat this
process for the rest of the seeds until we have sampled all seeds. For each
combination of seeds, we calculate the total seed frequency and find the
minimum total seed frequency among all combinations.

The key problem in the brute-force solution above is that it examines a lot of
obviously suboptimal combinations. For example,.....

...The above observation suggests that by summarizing the optimal solutions of
partial reads under a smaller number of seeds, we can prune the search space
of the optimal solution. Specifically, givenm (withm < x) seeds and a
substring U that starts from the beginning of the read, only the optimal m
seeds of U could be part of the optimal solution of the read. Any other
suboptimal combinations of m seeds of U should be pruned.

\---------------------------------------------

**Abstract**

> Motivation: Optimizing seed selection is an important problem in read
mapping. The number of non-overlapping seeds a mapper selects determines the
sensitivity of the mapper while the total frequency of all selected seeds
determines the speed of the mapper. Modern seed-and-extend mappers usually
select seeds with either an equal and fixed-length scheme or with an
inflexible placement scheme, both of which limit the potential of the mapper
to select less frequent seeds to speed up the mapping process. Therefore, it
is crucial to develop a new algorithm that can adjust both the individual seed
length and the seed placement, as well as derive less frequent seeds.

Results: We present the Optimal Seed Solver (OSS), a dynamic programming
algorithm that discovers the least frequently-occurring set of x seeds in an
L-bp read in O(xL) operations on average and in O(xL2) operations in the worst
case. We compared OSS against four state-of-the-art seed selection schemes and
observed that OSS provides a 3-fold reduction of average seed frequency over
the best previous seed selection optimizations.

