---
title: Do de Bruijn Assemblers Work in Color Space?
tags:
- ABI-SoLID
- de-bruijn
- transcriptome assembly
- genome assembly
- color space
categories:
- blog
---
We are revisiting a topic that we [touched long time
back](http://www.homolog.us/blogs/2010/02/15/the-mathematics-behind-color-
space-sequencing/) \- color space. Many researchers have ABI SOLiD machines
and they like to try out various new assembly programs like Trinity or
Contrail. Do de Bruijn graph-based assemblers work on color space data? Do
they need to be modified for Color space data?
<!--more-->

The answers are 'yes and no', and let us explain why. Based on our articles on
[de Bruijn graphs](http://www.homolog.us/blogs/category/de-bruijn/), one can
argue that the general description is applicable for any kind of text and does
not need to be restricted to nucleotide sequences. There is one important
difference though. In [this article](http://www.homolog.us/blogs/2011/07/28
/de-bruijn-graphs-i/), we showed that each node is formed with a K-mer
sequence and its reverse complement. Reverse complement of color space
sequences is done differently from reverse complement of nucleotide sequences,
as explained [here](http://www.homolog.us/blogs/2010/02/15/the-mathematics-
behind-color-space-sequencing/).

To answer the original question, all assemblers can work on color space data
after modification that correctly implements reverse complement rules for
color space. In fact, the change needed in the original code is very minor. To
learn how the modification is done, please take a look at the code of Velvet
assembler, which works for both nucleotide and color space data. Inside
various C files within 'src' directory of Velvet, search for "ifdef COLOR" or
"ifndef COLOR" blocks. That is where the modification for color space is done.

Some people mistakenly assume that if they rewrite their SOLiD data in pseudo-
nucleotide space, all programs written for nucleotide data will magically
work. That is wrong, because pseudo-nucleotide conversion merely replaces
0,1,2,3 by ATGC, but it does not change how reverse complementing is done for
the sequences. Reverse complementing of pseudo-nucleotide SOLiD data is not
done in the same way as reverse complementing of true nucleotide sequences.
That is why the assemblers will not work out of the box.

