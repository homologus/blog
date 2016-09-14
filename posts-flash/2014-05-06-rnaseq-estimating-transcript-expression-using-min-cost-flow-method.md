---
title: 'RNAseq: Estimating Transcript Expression using Min-cost Flow Method'
categories:
- rnaseq
---
We have been reading a paper -
<!--more-->

[A novel min-cost flow method for estimating transcript expression with RNA-
Seq](http://www.biomedcentral.com/1471-2105/14/S5/S15)

It proposes an alternative to expectation maximization methods for computing
RNAseq expression levels. (RSEM, sailfish).

> In this paper we propose a novel radically different method based on
minimum-cost network flows. This has a two-fold advantage: on the one hand, it
translates the problem as an established one in the field of network flows,
which can be solved in polynomial time, with different existing solvers; on
the other hand, it is general enough to encompass many of the previous
proposals under the least sum of squares model. Our method works as follows:
in order to find the transcripts which best explain, under a given fitness
model, a splicing graph resulting from an RNA-Seq experiment, we find a min-
cost flow in an offset flow network, under an equivalent cost model. Under
very weak assumptions on the fitness model, the optimal flow can be computed
in polynomial time. Parsimoniously splitting the flow back into few path
transcripts can be done with any of the heuristics and approximations
available from the theory of network flows. In the present implementation, we
choose the simple strategy of repeatedly removing the heaviest path.

The elegant part of the paper is in how it converted the RNA-seq expression
estimation problem to [min cost flow](http://en.wikipedia.org/wiki/Minimum-
cost_flow_problem). After the conversion is done, a number of standard
algorithms can be used to determine expression levels and there will not be
any need for time-consuming expectation maximization loops. The following
tutorials are useful for you to catch up with those standard procedures.

[min-cost flow -
introduction](http://www.columbia.edu/~cs2035/courses/ieor6614.S14/mcf.pdf)

[min cost flow tutorial - part 1](http://community.topcoder.com/tc?module=Stat
ic&d1=tutorials&d2=minimumCostFlow1)

[min cost flow tutorial - part 2](http://community.topcoder.com/tc?module=Stat
ic&d1=tutorials&d2=minimumCostFlow2)

