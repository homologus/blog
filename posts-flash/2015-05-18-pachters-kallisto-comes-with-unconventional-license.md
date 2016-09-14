---
title: Pachter's Kallisto Comes with Unconventional License
tags: []
categories:
- rnaseq
---
**This is being reposted from the bioinformatics blog.**
<!--more-->

We tested the latest and greatest RNAseq expression analysis program Kallisto
[discussed in this link](http://www.homolog.us/blogs/blog/2015/05/14
/lightweight-algorithms-for-rnaseq-expression-analysis-sailfish-kallisto-and-
salmon/). It comes with binary (for Mac and Ubuntu), and source code.

**Running the binary**

First we tested the binary code with the small data file already provided in
the test folder, and it worked without trouble as expected. We are going to
test on large files, but do not anticipate any problem either.

Remember this is an alignment-free method for RNAseq expression analysis.
Therefore, if you diligently aligned all your reads on to the expression
files, you may delete those large SAM/BAM files and proceed anew. The
execution of this program will probably take less time than deleting the large
SAM files from hard-drive - no kidding !

**Compiling the source**

Next, we tried to compile the code [downloaded from github](
https://github.com/pachterlab/kallisto). That hit a glitch ("CMake 2.8.12 or
higher is required. You are running version 2.8.9"). We tried to change the
CMakeLists.txt to "cmake_minimum_required(VERSION 2.8.9)", but that gave the
error - 'Unknown CMake command "add_compile_options"'. It seems like we need
to upgrade cmake to compile the source-code.

**Algorithm and code**

The algorithm of the method is explained in the [arxiv paper by Bray et
al.](http://arxiv.org/abs/1505.02710). It is an improvement over Sailfish,
because instead of splitting the reads into k-mers, this program combines
alignment and de Bruijn graph to do perform pseudoalignment of each read on
indexed reference file.

The code (~3500 lines of C++ code, ~5,500 lines with header) is fairly simple
to understand for those who are working on bioinformatics programs. It
leverages Heng Li's super-efficient kseq.h and
[SuperFastHash](https://code.google.com/p/smhasher/wiki/SuperFastHash), and
then builds the remaining blocks according to algorithm described above.

**License**

The license is very unusual and makes this program useless to build on. It is
against sharing/rebuilding, because borrowing from their code with destroy
your licensed code-base. Be very worried !

Let me explain. Most bioinformatics programs come with GPL or MIT/Berkeley-
type license, but this one adds 'for educational and research not-for-profit
purposes' making the license very restrictive and legally ambiguous. Let us
say you add a file from it into your bioinformatics code released under GPL.
Then you will be forced to add the same meaningless words into your GPL
license, which will spoil the license of your GPL-licensed code. Then there is
propagation effect. If someone else adds from your code, that person's code
will need to have the same extra words and so on. Similarly, you cannot use
their code in a cloud application along with your data, because you cannot
guarantee that the viewer of your data does not come from a company.

The entire license is reproduced below with emphasis added on the extra (and
legally ambiguous) part.

> Copyright 2015. The Regents of the University of California (Regents). All
Rights Reserved. Permission to use, copy, modify, and distribute this software
and its documentation **for educational and research not-for-profit
purposes**, without fee and without a signed licensing agreement, is hereby
granted, provided that the above copyright notice, this paragraph and the
following two paragraphs appear in all copies, modifications, and
distributions. Contact The Office of Technology Licensing, UC Berkeley, 2150
Shattuck Avenue, Suite 510, Berkeley, CA 94720-1620, (510) 643-7201, for
commercial licensing opportunities.

Created by Nicolas Bray, Harold Pimentel, Pall Melsted and Lior Pachter,
University of California, Berkeley

IN NO EVENT SHALL REGENTS BE LIABLE TO ANY PARTY FOR DIRECT, INDIRECT,
SPECIAL, INCIDENTAL, OR CONSEQUENTIAL DAMAGES, INCLUDING LOST PROFITS, ARISING
OUT OF THE USE OF THIS SOFTWARE AND ITS DOCUMENTATION, EVEN IF REGENTS HAS
BEEN ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.

REGENTS SPECIFICALLY DISCLAIMS ANY WARRANTIES, INCLUDING, BUT NOT LIMITED TO,
THE IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR A PARTICULAR
PURPOSE. THE SOFTWARE AND ACCOMPANYING DOCUMENTATION, IF ANY, PROVIDED
HEREUNDER IS PROVIDED "AS IS". REGENTS HAS NO OBLIGATION TO PROVIDE
MAINTENANCE, SUPPORT, UPDATES, ENHANCEMENTS, OR MODIFICATIONS.

