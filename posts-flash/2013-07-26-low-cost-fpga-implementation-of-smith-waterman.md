---
title: Low-cost FPGA Implementation of Smith-Waterman
tags: []
categories:
- blog
---
A pair of Bachelor thesis reports may be of interest to the readers.
<!--more-->

[Acceleration of the Smith-Waterman algorithm for DNA sequence alignment using
an FPGA
platform](http://repository.tudelft.nl/view/ir/uuid%3A70bde5f3-f929-4267-9e3e-
213a090f724c/)

Barry Strengholt Matthijs Brobbel

> With the sequencing of DNA becoming cheaper and the resulting stack of data
growing bigger, there is a big challenge for both engineer and biologist.
Researchers are limited by their computational power. In this thesis, rst an
overview of sequence alignment algorithms will be given. Then a method to
store the values of the similarity score matrix of the Smith-Waterman
algorithm di fferentially will be presented. And finally, a description of the
system approach used to design an accelerator, which implements this method,
will be given. Implementation of the system design on an Artix-7 XC7A200T-2C
FPGA, could lead to a total performance of 94 GCU/s. This is a speed up of 5x
compared to conventional CPUs.

[Low-Cost Smith-Waterman
Acceleration](http://repository.tudelft.nl/view/ir/uuid%3A9153ff2c-
13c5-4be0-8446-fe33b88ab274/)

Matthijs Geers Fatih Han C aglayan Roelof Willem Heij

> Due to advancing technology, genetic sequencing has become cheaper over the
years. This has caused the demand for computational power to grow even faster
than Moore's law. To remedy this problem, we analyzed low-cost hardware
solutions to parallelize the computational part of the genetic sequencing. We
proposed a novel method for calculating the score matrix of the Smith-Waterman
algorithm, which solves the bandwidth bottleneck in earlier solutions. This
method calculates the score matrix di fferentially and a bu er keeps track of
the maximum value. Due to the nature of the Smith-Waterman algorithm, the
resulting implementation can do the calculations fully in parallel. Since it
ts on an Artix 7 XC7A200T chip 908 times, this leads to more than a twelve-
fold improvement in performance/price compared to SciEngines' Rivyera FPGA
supercomputing platform.

