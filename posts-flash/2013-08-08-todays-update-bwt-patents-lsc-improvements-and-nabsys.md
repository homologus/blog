---
title: Today's Update - BWT Patent, LSC Improvements and Nabsys
tags: []
categories:
- blog
---
**Patent on BCR Algorithm**
<!--more-->

Few weeks back, we wrote about the patents on various BWT-related
bioinformatics algorithms.

[Bioinformatics Patents on Burrows Wheeler
Transform](http://www.homolog.us/blogs/blog/2013/07/20/bioinformatics-patents-
on-burrows-wheeler-transform/)

We emailed Dr. Anthony Cox asking about what other bioinformaticians should do
to use his work, and he was kind enough to reply. Firstly, he corrected us on
the status of the patent. It is only a pending application and not an assigned
patent. Regarding use of his work, the rules are the same as what he wrote in
the comment section of a previous thread -

> My understanding of the license is that it is meant to allow you to do
pretty much whatever you want with the code install, use, distribute, modify
for non-commercial purposes. Moreover, unlike some definitions of non-
commercial purposes, my understanding is the license is meant to permit non-
commercial use at commercial entities, e.g. in the R&D; department of a pharma
company.

We request you to read the entire comment for other details.

[Academic Bioinformaticians Uncomfortable with Illuminas Publication of
Variant Caller](http://www.homolog.us/blogs/blog/2013/06/05/academic-
bioinformaticians-uncomfortable-with-illuminas-publication-of-variant-caller/)

**LSC**

LSC is a pipeline like PacBioToCA for error-correcting PacBio reads. Erich
Scwartz recommended it to us and we wrote about LSC
[here](http://www.homolog.us/blogs/blog/2013/02/05/lsc-an-alternative-to-
pacbiotoca-for-error-correction-of-pacbio-reads/).

![Capture](http://www.homolog.us/blogs/wp-
content/uploads/2013/08/Capture13-300x54.png)

You can check the updates in this
[link](http://www.stanford.edu/~kinfai/LSC/LSC.html).

> Very IMPORTANT updates:

Support for Bowtie2 and RazerS3 as initial aligners. Now, BWA, Bowtie2,
RazerS3 and Novoalign work in LSC. Please see the comparison details of
aligners in the "Short read - Long read aligner#manual".

Added SR length coverage percentage on LR (SR-covered length/full length of
corrected LR) to corrected_LR output file. Here is an example, where the last
number 0.82 is the SR length coverage percentage on LR:

>m111006_202713_42141_c100202382555500000315044810141104_s1_p0/18941/365_1361|
0.82

Added support for three modes for step-wise runs:

mode 0: end-to-end

mode 1: generating LR_SR.map file

mode 2: correction step

Generating FASTQ output format based on correction probability given short
read coverage. Please refer to LSC paper and manual page for more details. You
can select well-corrected reads for downstream analyses by using the quality
in FASTQ output or SR length coverage percentage above. Please the the
filtering in the "Output#manual".

**Nabsys**

In a previous thread, we covered NabSys based on discussions in Omics! Omics!
blog.

[NabSys Unveiled (Omics! Omics!
Blog)](http://www.homolog.us/blogs/blog/2013/02/25/nabsys-unveiled-omics-
omics-blog/)

@sjackman forwarded a link from NabSys webpage that is [very informative on
the technology](http://www.nabsys.com/Technology.aspx).

<iframe width="560" height="315" src="http://www.youtube.com/embed/HV0aWVrDM2U" frameborder="0"> </iframe>

