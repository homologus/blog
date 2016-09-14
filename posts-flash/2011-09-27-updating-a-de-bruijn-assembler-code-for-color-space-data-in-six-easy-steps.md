---
title: Updating a de Bruijn Assembler Code for Color Space Data in Six Easy Steps
tags:
- ABI-SoLID
- de-bruijn
- Trinity
- color space
- contrail
categories:
- blog
---
The entire process should take about an hour or so depending on how long you
spend on the last step.
<!--more-->

**Step 1.** Go to your local supermarket and bring a bottle of good wine [estimated time - 20 minutes]. 

**Step 2.** Open the bottle and pour wine in a glass [estimated time - 10 minutes]. 

**Step 3.** You are allowed to taste the wine at this time, but please do not drink too much. We got work to do [estimated time - 7 minutes]. 

**Step 4.** Switch on your computer and locate the folder with assembler code [estimated time - 3 minutes]. 

**Step 5.** Find the C or Java subroutine within the code that defines the reverse complement of a sequence, and update it for color space. The only difference between a nucleotide-space assembler and a color-space assembler is how the reverse complement of a k-mer is defined. [As you remember](http://www.homolog.us/blogs/2010/02/15/the-mathematics-behind-color-space-sequencing/), reverse complement in color space is simply the reverse of the string, whereas the step is more complicated for nucleotide data. 

[estimated time - 5 minutes].

**Step 6.** You are done. Enjoy your wine. [estimated time - 15 minutes or longer]. 

\----------------------------------

We followed the above procedure to update Trinity transcriptome assembler for
color space. Trinity is a combination of three independent programs -

i) **Inchworm** goes through the entire collection of reads and uses a greedy
algorithmic strategy to determine transcripts at a coarse level.

ii) **Chrysalis** parses the entire collection of reads into smaller groups
based on transcripts that came out of inchworm.

iii) **Butterfly** carefully assembles genes from every group, and defines
gene structure, alternate splicing, etc.

We found two reverse complement functions in sequenceUtil.cpp file of Inchworm
and modified them. We also modified one function in DNAVector.cpp of
Chrysalis. Butterfly did not seem to have any RC function. The methods for
compiling and running the codes should not change, because the changes are
minor. However, remember that you need to run the color-space version on
psedo-nucleotide data (A/T/G/C), not sequences with 0/1/2/3. You can either
write your own code for pseudo-nucleotide conversion, or use ABI's
solid_denovo_preprocessor.pl routine.

**Testing 1. Simulated library ** We first tested the modified code on simulated unpaired short read data from one gene. We generated perfect 50-mer reads from the gene in both nucleotide and color space. The results of regular trinity executed on nucleotide space read library and color-space trinity on color space reads were identical. 

**Testing 2. Illumina nucleotide library** Next, we tested the code on an Illumina paired end library for 45 genes on which we are currently working for another project. We ran the regular trinity on the original library, and modified trinity on the library of reads converted to color space. Again the results were identical. 

**Testing 3. (SOLiD library)** [A collaborator of us](http://armbrustlab.ocean.washington.edu/people/armbrust) was very generous to share a SOLiD RNAseq library with us, and we tested the modified trinity on this library. This run took several hours, and after completion, we got only 1403 genes. Over 90% of the genes aligned on the reference genome. 

The number of genes in Test 3 seems very low. Previously, when we ran trinity
on various Illumina libraries of similar size, the number of genes came
between 30,000-100,000. What is going on?

It seems to us (based on Test 1 and 2) that the conversion of the code to
color space is correctly done, but most likely the default parameters for
trinity need to be adjusted for color space data. Trinity assumes K-mer size
of 25, but our previous experience with ABI data suggests that the amount of
noise is usually high to make a large fraction of 25-mers incorrect. However,
you already learned that single error in SOLiD data is far less harmful than
single error in Illumina data. I think a comparison is more appropriate, if
SOLiD data are cleaned for all such single space changes.

If you like to test the code and report how it works, please email us at
samanta@homolog.us. Those, who already sent us email, should receive a copy
shortly.

