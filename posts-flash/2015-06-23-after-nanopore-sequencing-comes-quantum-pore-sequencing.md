---
title: After Nanopore Sequencing  Comes Quantum Pore Sequencing
tags: []
categories:
- blog
---
[Jason Chin wrote](https://gist.github.com/cschin/be6c52a08a9535839417) \-
<!--more-->

> I currently work for PacBio as a bioinformatist developing some methods to
handle single molecule data and genome assembly properly.

Recently, I feel I am so lacking of vision. I have spent most of my time
helping to develop methods in hope that they will be useful for the scientific
community to use PacBio data. While we were developing those methods, as far
as I could tell, many of those ONT fans had zero vision about them. We openly
revealed those methods for the benefit to the scientific community to
understand the value of PacBio's and PacBio-like data. We naively assumed ONT
would generate some great data with raw single molecule read accuracy > 96% as
what Clive presented in 2012 AGBT. If so, those ONT fans would not need to use
any of those methods we had developed. After a while, we find out that some of
the visionary ONT fans are finally "inspired" to use some of our methods for
processing some ONT data and publishing papers to show some values which some
of those fan questioned about before. Without any new inspiration to me, I
feel so dwarfed thinking how visionary the company was when they promised to
build a world class bioinformatics center to develop bioinformatics method in
Oxford back in 2011 ( https://www.genomeweb.com/informatics/oxford-nanopore-
opens-new-bioinformatics-center-cambridge-will-expand-informatic).

Maybe it is just also from many other questionable scientific and business
practices that trigger me to feel that I am in my mid-life crisis. I think one
good way to get out of it is to learn to be a visionary man like
@BioMickwatson. So, I start to think how I can start my own company to develop
a quantum pore DNA sequencer soon.

Here is my vision: all sequencing and bioinformatics will be done with quantum
computer with latest spintronics on a single graphane sheet. All you have to
do is to put the graphane patch on the bottom of your Apple Watch, your genome
sequence data will be transferred to the Cloud every 15 minutes (through HLTE,
Hype-long-term evolution network, wireless throug hyperspace spectrum, of
course). After analyzing with STP-WGAA (space-time-population whole-genome-
assembly-association), the drug you need to keep your visionary view for the
day will be on your office desk even before you get into your office in a
Google self-driving car or through Elon Musk's Hyperloop. Not only that,
proper p-value for keeping your visonary view against whatever null hypothesis
will be calculated and send to journal editors and reviewers to justify
certain words used in the conclusion section of a news-worthy paper. Or,
better, it also automagically produces papers because they are news-worthy as
no scientific study is actullay needed to be done to get scientific results.
(The best part is that it fixes my crappy English spelling and grammar in the
process.) What a wonderful world!! The imagination is unlimited!! I will be
retired in months after successfully hiring my CPO while many graduate
students or postdocs will be figuring how to pipette into a graphene sheet or
using a spintronics driving quantum computers in the years to come. (Did I say
no pipetting nor bioinformatics needed?)

Life is too short. Now I feel inspired and visionary again. I should be hiring
soon. First start with a CPO. What can be a more exciting job than a CPO!! Not
surprisingly, my prototype already shows the p-value that this company will
not be successful is less than 0.05. Join me! No resume of scientific research
experience required. Experience for proper commercialization or production
development undesirable. No one needs to write a product specification anyway.
Rejection for sure if you try to make any scientific or business sense out of
this. Also, if you already have public funding resource, our investors will
prefer that you keep getting paid by that. High K-index impact guaranteed
among cargo cult scientists' club.

Opinion mine. Writing in a personal computer and in personal time. All Facts.

\-------------------------------------------------------

Readers please rank the above vision in a 1-10 scale, with the following post
measuring as 10.

[Food, fantasies and the future](http://www.foodsecurity.ac.uk/blog/2013/09
/food-fantasies-and-the-future/)

> What will next generation livestock farms look like? Mick Watson examines
scenarios and what we should do to get there.

Farmer Jane opened the gate and walked along the track that meandered along
the side of her cattle barn. Chuckling to herself, she was old enough to
remember how disease surveillance used to be done. It was so much easier now.
Inside the barn, she approached the first of the ten cattle that had been
randomly isolated, reached into her bag and took out the first of her
SeqPensTM. Removing the protective lid, she briefly pressed the steel nib to
the neck of the first animal then stood back to wait for the lights to change.

The painless microneedle pens would capture a tiny amount of blood and extract
all of the DNA in the sample, whether from the cow, or the myriad parasites
and pathogens that could infect her. The DNA would pass through an engineered
nanopore that would determine the exact sequence in a matter of seconds.

\----------------------------------------------------

For those stuck in the mundane world of cost and quality, David Eccles [wrote
an informative reply](http://www.homolog.us/blogs/blog/2015/06/18/oxford-
nanopore-fans-are-asking-three-questions-today/#comment-129351) regarding the
questions asked by me and others. I am a bit confused about Reply 2 and need
help from my knowledgeable readers.

> 1\. Price is a bit steep at the moment, but that should change in the near
future once ONT sorts out the issues with processing all the data generated in
fast mode (see my update post for more information). Paying $900 for
400-2000Mbp of sequence is quite a lot, but the fast mode will produce that
amount in about 3 hours (with a 48h run still possible). ONT is also planning
to introduce a lower cost (around $300) for a 3-hour run time for the fast-
mode runs. If cost is an issue, Id recommend waiting a couple of months for
the output to increase.

2\. Read error rate can be anything from 6% to 26%, depending on the alignment
strategy and what you consider as errors. The 6% is using only 2D reads that
pass the ONT read QC process (i.e. they end up in the pass folder), mapped
with LAST using a custom alignment matrix, and only considering SNPs (its 11%
including INDELs as well). The 26% is the worst mapping from ~20 runs using
BWA-mem in ont mode, from all 2D reads. Both the 11% and 26% error rates came
from the same set of data, 5 labs sequencing an E. coli K12 strain. Apparently
PacBio INDELs can be fairly long; for my results the INDELs were typically
1-2bp, with 95% of INDELs being 8bp or less.

3\. ONT said that explicitly that they dont want competitors to have access to
their device through MAP. I think its also reasonable to assume that abusers
of the technology will be prevented from further access as well. I havent
asked anyone at ONT whether that would extend to people who are excessively
negative about the technology Ill ask on the MAP wiki.

4\. MinION metrics are *really* difficult to pin down. Read length doesnt make
much sense; 8-10kb is a common target, but greater than 200bp would be my most
precise statement, although thats probably going to change soon with an
improved software workflow for short reads. Output is currently 400-2000Mbp
for a full-length good run, but there are a lot of people in MAP who arent
reporting on the community and are getting closer to 10-100Mbp per run (which
I only found out from speaking to people at the conference). Note that the
MinION can be stopped at any time, with the minimum reasonable run time to get
sequence being about 15 minutes. All these metrics will change dramatically
with fast mode (~30x more sequence), and again with the MkII chips (6x run
time, 6x number of sequencing channels).

