---
title: We See the Light - Source Code Should be Published
tags: []
categories:
- blog
---
After thinking through various arguments for or against publishing source
codes with NGS papers, we came to agree with Titus Brown. [All objections
raised by us](http://www.homolog.us/blogs/2012/09/05/thoughts-on-anecdotal-
science-by-ctb/) appear more like exceptions and do not show up in case of
>99% of NGS-related research reports. [That stat we threw in is purely off a
hat...we cannot produce source code :)]
<!--more-->

Let us explain why there should be no serious objection against publishing
source codes. The rule of scientific reporting is to clearly express all steps
so that anyone else can reproduce the experiment by reading the report. For
computational 'experiment', those steps constitute of starting from raw reads
and running various programs/scripts to get to the result. Ideally, the author
is supposed to report every small parameter used in every step so that another
person can properly reproduce the steps. So, by allowing an author to post
source code, the community is telling him - 'Ok, you can be a bit sloppy in
your reporting in supplementary text, as long as you give us your jumbled up
PERL/python scripts. We will help you fill up the holes.' The community is
giving the author an easy way out, and that is a bargain most authors should
be able to accept. However, few stubborn authors may choose the more difficult
option of full reporting of all parameters/steps, and we are ready to let them
do so provided they do the job properly.

**Exceptions** \- Should someone be dragged to expose his well-written C++ code? For example, let us say a lab develops an integrated code for a submitted paper and another ongoing 'secret' research project not expected to be published in another 6 months. Would not publishing source code compromise their intentions by giving heads up to the competitor? One can always come up with other reasons not to give codes away, but we suspect the primary excuse will be 'competitive reason'. We believe the authors can always publish a replica code, as long as it goes from A (raw data) to Z (final results) in the same manner as described in text. The 'replica' rule should take care of all objections raised by us earlier. 

Basically, the primary goal here is to let others reproduce the computational
experiment. We are not after well-thought out class structures of various
objects designed by the programmer. Therefore, a sloppily written PERL code
implementing the same algorithm is good enough for the reporting task.

\------------------------

On a related, but somewhat different matter, we recently found out that the
authors of [sea urchin RNAseq paper](http://www.homolog.us/blogs/2012/07/13
/question-for-the-readers-what-is-the-convention-for-submission-of-raw-reads-
these-days/) posted their raw reads in the SRA database. However, when we
checked the reads, we found that they were all 162 nt single-ended Illumina
reads, whereas the experiment got paired end. It took us few minutes to figure
out that the authors joined the reads by using some other method, and
submitted the joined reads.

That was very nice of the authors to help potential users skip one or more
step in analysis, but joined reads are not raw reads coming out of machine and
do not have the same statistical structure as raw reads.

At this point, we do not know whether to thank authors for thoughtfulness, or
whether to be a [PITA](http://www.urbandictionary.com/define.php?term=PITA) by
asking for raw reads.

