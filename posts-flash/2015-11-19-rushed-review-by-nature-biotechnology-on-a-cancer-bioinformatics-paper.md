---
title: Rushed Review by Nature Biotechnology on a Cancer Bioinformatics Paper?
tags: []
categories:
- blog
---
One of our readers, who is a PhD student, has been struggling with trying to
figure out what is going on with the paper - "[Comprehensive analysis of
cancer-associated somatic mutations in class I HLA
genes](http://www.nature.com/nbt/journal/v33/n11/full/nbt.3344.html)". The
corresponding author is broadster Gad Getz, who did not respond to his email
correspondences.
<!--more-->

![GadGetz](http://www.homolog.us/blogs/wp-content/uploads/2015/11/GadGetz.png)

> In addition to his role at the Broad, Getz is a co-principal investigator in
the Genome Data Analysis Center (GDAC) of the NCI/NHGRI TCGA (The Cancer
Genome Atlas) project; a co-leader of the International Cancer Genome
Consortium (ICGC) Pan-Cancer Analysis of Whole Genomes (PCAWG) project; a co-
principal investigator of the Broad-led NCI Cloud Pilot; and a member of
various NCI advisory committees. In addition, Getz directs the Bioinformatics
Program at the Massachusetts General Hospital Cancer Center and Department of
Pathology and serves as an associate professor of pathology at Harvard Medical
School. Getz is also the inaugural incumbent of the Paul C. Zamecnik Chair in
Oncology at the MGH Cancer Center. **He has published numerous papers in
recent years in prominent journals** that describe new genes and pathways
involved in different tumor types.

Maybe it is time for him to publish in real scientific journals instead than
'prominent' magazines.

\--------------------------------------------------------

Here are the specific questions -

> The article compares a number of algorithms, but provides no details about
any of the software versions or parameter settings. It's in contrast to the
editorial position presented in
<http://www.nature.com/nbt/journal/v33/n4/full/nbt.3202.html> which states
"Since last October, all Nature journals have required that authors declare
the location and accessibility of any custom code and software central to the
main claims in a paper ..." If the method has double the accuracy of some
existing methods, I'd like to see what parameters they used on the existing
methods or what versions they ran. Remarkably, the authors didn't even provide
any of the parameters of their own software, making none of their analyses
reproducible. With poor quality documentation like shown below, it would be
necessary to have reproducible code.

Input parameters:

-bam: path to the BAM file to be used for HLA typing 

... ...

-format: fastq format (STDFQ, ILMFQ, ILM1.8 or SLXFQ; see Novoalign documentation) 

Source : <https://www.broadinstitute.org/cancer/cga/polysolver_run>

Why is the input a BAM file, but there's a parameter to specify the FASTQ
format ? Which parameters are optional and which are mandatory ? The
documentation must have been an afterthought.

\--------------------

> I've also noticed they have a crucial supplementary table 11 missing from
their supplementary materials and described as being available in dbGaP, but
is nowhere to be found.

