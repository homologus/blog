---
title: On Algorithmic Complexity of Biomolecular Sequence Assembly Problem
tags: []
categories:
- blog
---
In twitter, we noticed [this
paper](http://cs.nyu.edu/mishra/PUBLICATIONS/14.ALCOB.pdf) with the same title
as of this post. It is written by G. Narzisi, Bud Mishra and Michael Schatz
and is accepted by [1st International Conference on Algorithms for
Computational Biology, AlCoB 2014 to be held in Tarragona,
Spain](http://grammars.grlmc.com/alcob2014/acceptedpapers.php). Michael Schatz
is an expert in genome assembly and we covered his work several times.
<!--more-->

The paper can be best described as a review or synthesis of existing ideas on
sequence assembly.

> Because of its connection to the well-known NP-complete shortest superstring
combinatorial optimization problem, the Sequence Assembly Problem (SAP) has
been formulated in simple and sometimes unrealistic string and graph-theoretic
frameworks. This paper revisits this problem by re-examining the relationship
between the most common formulations of the SAP and their computational
tractability under different theoretical frameworks. For each formulation we
show examples of logically-consistent candidate solutions which are
nevertheless unfeasible in the context of the underlying biological problem.
This material is hoped to be valuable to theoreticians as they develop new
formulations of SAP as well as of guidance to developers of new pipelines and
algorithms for sequence assembly and variant detection.

It discusses shortest superstring problem, de Bruijn graph and overlap graph.
That is along the line of traditional way to discuss genome assembly
algorithms. Unfortunately, we do not like the paper for two reasons.

(a) The paper fails to cover the fourth chain of developments starting from
Batzoglou's MIT thesis, going into ARACHNE and later integrated into R. Li's
human paper and SPAdes, and that is the incorporation of mate pairs.
Incorporation of paired reads increases the effective read length and thus
allows easier resolution of repeats. In fact, R. Li's human paper nicely
discussed statistical analysis of distance between repeats in human genome and
that analysis is possibly the reason behind BGI's subsequent experimental
strategy of building longer and longer mate pairs. Similarly, Pevzner made
significant conceptual improvement in his de Bruijn graph (Euler) methodology,
when his SPAdes group came up with rectangular graphs to incorporate mate
pairs. Without having that conceptual block being added, the readers are
getting incomplete picture of algorithmic development so far.

(b) The paper fails to cover the statistical aspect of sequence assembly
(maximum likelihood estimation in Kececioglu's thesis and or distance
statistics in SPAdes paper) and presents the assembly problem in purely
computer science terms (NP-complete). The abstract says -

> For each formulation we show examples of logically-consistent candidate
solutions which are nevertheless unfeasible in the context of the underlying
biological problem.

"Logically-consistent" is code-word for mathematically neat but practically
unrealistic solution. For example, a mathematically neat quadratic equation
can find that a person weighs negative. In the same vein, an elegant computer
algorithm (mathematical construct) can obtain hundreds of cool and unrealistic
solution.

The reason we say all these is because we believe the authors wrote the paper
for a computer science audience and tried to pose the problem in terms of what
is known by such an audience and moving outward. In our opinion, they would
have done their audience justice by first presenting all experimental tools
and limitations (i.e. (i) what a typical genome is like, (ii) the sequencing
methods) and then posing various algorithmic ways to approximate that reality.

As always, we encourage our readers to present their thoughts and express
disagreement with us.

