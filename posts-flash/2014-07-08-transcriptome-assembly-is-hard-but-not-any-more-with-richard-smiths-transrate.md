---
title: "'Transcriptome Assembly is Hard', but Not Any More with Richard Smith's Transrate"
categories:
- rnaseq
---
Richard Smith-Una, whose work was covered in our blog, releases a new quality
assessment program (transrate) that we surely like to check out.
<!--more-->

>

Transcriptome assembly is hard. The algorithms are complex, the data are
messy, and it's often not clear how to determine whether an assembly is
suitable for answering a biological question.

Transrate helps by examining your assembly in detail and providing insight
about its quality and usefulness in various situations. This can allow you to
choose between assemblers and parameters, and helps you decide when to stop
trying to improve the assembly.

Overview

Transrate analyses an assembly in three key ways:

by inspecting the contigs themselves

by mapping reads to the contigs and inspecting the alignments

by aligning the contigs against proteins from a related species and inspecting
the alignments

You can read about these analyses in detail on the transcriptome assembly
metrics page.

Installation

If you've got Ruby v2.0.0 or later, simply install Transrate with the command:

$ gem install transrate

Transrate depends on some external tools that can't be installed by the
transrate installer, including BLAST+ and Bowtie2. You can install these
dependencies yourself, or you can let Transrate do it for you by running the
command:

$ transrate --install-deps

If you don't have at least v2 Ruby installed, you should install the latest
version using the Ruby Version Manager: RVM.io, then install transrate as
above.

The command-line interface

Running transrate --help will show you the command-line interface:

Transrate v0.2.0 by Richard Smith-Unna

and Chris Boursnell.

DESCRIPTION:

Analyse a de-novo transcriptome

assembly using three kinds of metrics:

1\. contig-based

2\. read-mapping (if --left and --right are provided)

3\. reference-based (if --reference is provided)

Github site to download code is [here](https://github.com/Blahah/transrate).

Manual is available [here](http://hibberdlab.com/transrate/).

