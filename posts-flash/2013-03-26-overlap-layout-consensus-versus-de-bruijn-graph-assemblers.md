---
title: Overlap-Layout-Consensus versus de Bruijn Graph Assemblers
tags: []
categories:
- blog
---
In the first section of our [tutorials on de Bruijn graph
(dBG)](http://www.homolog.us/Tutorials/), we motivated the use of dBG-
assemblers by saying that they assembled repeat regions better than overlap-
layout-consensus (OLC) assemblers. One reader objected to that claim -
<!--more-->

> You make it look like OLC may incorrectly resolve repetitions. This is not
the case, at least no more than a dBG.

Our original text was written based on [Pavel Pevzner's 2001
paper](http://www.ncbi.nlm.nih.gov/pmc/articles/PMC55524/) \-

> For the last 20 years, fragment assembly in DNA sequencing followed the
overlaplayoutconsensus paradigm that is used in all currently available
assembly tools. Although this approach proved useful in assembling clones, it
faces difficulties in genomic shotgun assembly. We abandon the classical
overlaplayoutconsensus approach in favor of a new euler algorithm that, for
the first time, resolves the 20-year-old repeat problem in fragment assembly.
Our main result is the reduction of the fragment assembly to a variation of
the classical Eulerian path problem that allows one to generate accurate
solutions of large-scale sequencing problems. euler, in contrast to the celera
assembler, does not mask such repeats but uses them instead as a powerful
fragment assembly tool.

Who is right - Pevzner or our reader? Answer is both, and here is how. Pevzner
was correct in 2001, when he wrote his article, and our reader is correct in
2013. It is because neither dBG-based assemblers, nor OLC-assemblers are
static. Both types of assembly algorithms are being improved based on
knowledge derived from the other. When Pevzner wrote his paper, he showed
significant improvement in assembly quality with his new algorithm. That
changed with [string graph assembler](http://www.homolog.us/blogs/category
/string-graph-assembler/), an OLC algorithm introduced in 2010-11, which took
care of many drawbacks of other OLC approaches on short reads. Where do two
approaches stand currently? Our reader provides further perspectives -

>

Yes, it is likely that OLC assemblers back then had heuristics which caused
misassemblies. But this is not a flaw of the OLC paradigm itself. Also,
perhaps the "difficulties" meant by Pevzner is high computational complexity.

While it is true that OLC corresponds to a NP-hard problem (hamiltonian path)
and dBG has a polynomial-time solvable problem (eulerian path), actual dBG
assembly using reads information is NP-hard (it's called de Bruijn super-walk
in the literature).

\--------------------------

Edit.

Our reader Jason Chin ?@infoecho chimed in and suggested us to take a look at
[David Tse's paper](http://arxiv.org/abs/1301.0068 ).

> @homolog_us

I like David Tse's approach in answering these question better.

http://arxiv.org/abs/1301.0068

We encourage readers to take a look. [We posted the link to that paper in an
earlier commentary](http://www.homolog.us/blogs/2013/01/05/optimal-assembly-
for-high-throughput-shotgun-sequencing/), and had many thoughtful comments
from our readers.

