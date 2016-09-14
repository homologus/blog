---
title: Testing SOAPdenovo2 Prerelease - IV (building contigs)
tags:
- SOAPdenovo
categories:
- blog
---
SOAPdenovo2 runs through the following steps -
<!--more-->

(i) generate the de Bruijn graph and store it ('pregraph' option),

(ii) analyze the de Bruijn to assemble contigs,

(iii) map all reads on to the contigs,

(iv) build scaffolds by combining contigs.

Today, we will explore the second step.

The command to run is -

**SOAPdenovo-63mer-v2.04.3 contig -g outPG**

where outPG is the pregraph generated from the previous step.

There is very little to write about the module. We typed the command and went
to get a coffee. The results were ready, when we came back. I guess we need a
next-generation coffee machine :)

Following files were created:

**outPG.contig** \- This is the contig file and is in fasta format. Here are the detailed stats given by SOAPdenovo2 - 

> 516528 ctgs longer than 100, sum up 538242466bp, with average length 1042

the longest is 48565bp, contig N50 is 2861 bp,contig N90 is 445 bp

4039233 contigs longer than 46 output.

**outPG.ContigIndex** \- A text-based index file that likely links the contigs and edges. We have not spent much time figuring out the details. 

**outPG.Arc, outPG.updated.edge** \- Two text output file. 

Finally, here is the full set of parameters for users interested in exploring
further.

> contig -g inputGraph [-R] [-M mergeLevel -D EdgeCovCutoff]

-g  inputGraph: prefix of input graph file names 

-R (optional) resolve repeats using information generated in pregraph step, works only if -R is set in pregraph step too, [NO] 

-M  mergeLevel(min 0, max 3): the strength of merging similar sequences during contiging, [1] 

-D  EdgeCovCutoff: edges shorter than (2*K+1) with coverage no largert than EdgeCovCutoff will be deleted, [1]

