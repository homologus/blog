---
title: Step by Step Guide on Genome Assembly with blasr and python
tags: []
categories:
- blog
---
[Here](http://nbviewer.ipython.org/urls/raw.github.com/cschin/Write_A_Genome_A
ssembler_With_IPython/master/Write_An_Assembler.ipynb) is one of the most
informative blog post on genome assembly from our friend Dr. Chen-Shan Chin.
<!--more-->

> I am not sure it is right thing to do some coding in a vacation. (See this
tweet, not sure if I would agree.) Anyway, before the vacation, I decided to
organize whole bunch of random papers I collected in the last few years in my
laptop. I eventually felt that I should read some of some theoretical papers
about genome assembly again. I grabbed Gene Meyer's paper, and started to
think about the problem about constructing unitigs (high-confident contigs).
Before I tried to read the paper in detail, I just felt maybe that it was
useful to write some quick code to check out what real data looked like. I
started writing some code visualizing the local overlapping and generating the
global overlapping graph. It was pretty straight forward and quite inspiring
from the visualization. The visualization motived me to write more ad-hoc code
in IPython to go beyond generating simple visualization during the vacation. I
started to implement a very simple greedy algorithm to connect the input DNA
fragments. Eventually, I found I can atucally get the whole genome assembly
right!! This Notebook shows the work step by step toward a simple genome
assembler for long read data using IPython and Python.

Please continue reading [at this link](http://nbviewer.ipython.org/urls/raw.gi
thub.com/cschin/Write_A_Genome_Assembler_With_IPython/master/Write_An_Assemble
r.ipynb).

