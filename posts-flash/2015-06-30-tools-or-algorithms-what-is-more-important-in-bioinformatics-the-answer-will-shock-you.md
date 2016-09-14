---
title: Tools or Algorithms, What is More Important in Bioinformatics? - The Answer
  Will Shock You
tags: []
categories:
- blog
---
There are often discussions about whether the bioinformaticians should spend
more time thinking about better algorithms or building more user-friendly
implementations. The answer is neither, as [a cancer benchmarking study found
out](http://biorxiv.org/content/early/2014/12/24/012997). Quoting from 'A
Comprehensive Assessment of Somatic Mutation Calling in Cancer Genomes' -
<!--more-->

> We also detected distinct clustering of different analysts. **Even though
analysts used similar combinations of software in their pipelines, very few
similarities were detected in their calls. The combination of software is not
as critical as how each piece of software is applied and what settings are
applied.** A slight correlation of true positive SSM calls of pipelines using
MuTect and Strelka can be seen (Figure 4). Data analysis pipelines are
constructed by integrating software from diverse sources. In many instances
the approaches used in the different software and the assumptions made therein
are not evident to the user and many parts are black boxes. In order to
account for unknowns, pipeline developers resort to calibrating their
pipelines against known results, for example from a genotyping experiment done
on similar samples, and by using combinations of tools for the same process
step, assuming that a result shared by two different approaches has a higher
likelihood to be correct. Of note is that many of the pipelines apply multiple
tools for the same process step in their pipeline and then use intersects to
weight calls. This practice, together with good use of blacklists, results in
best outputs. No best tools emerged from our benchmark and it is also clear
that no strict best threshold settings exist. **However, it is clear that how
analysts use their pipeline is critical for the quality of their output.**

