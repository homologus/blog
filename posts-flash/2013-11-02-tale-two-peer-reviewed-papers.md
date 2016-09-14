---
title: A Tale of Two 'Peer Reviewed' Papers
tags: []
categories:
- blog
---
Long, long time ago, it was believed that highly specialized work of one
scientist could be best evaluated by another scientist working in the same
field. For example, in 1993 Andrew Wiles of Princeton proved Fermat's last
theorem and [explained his work to his Princeton colleague Nick
Katz](http://en.wikipedia.org/wiki/Wiles'_proof_of_Fermat's_Last_Theorem).
When Wiles submitted his paper later that year, Dr. Katz was appointed as a
peer reviewer. He evaluated every step of the proof by having back and forth
discussions with Wiles, and at one point helped Wiles identify a hole in his
method. It took Wiles over one year to resolve the problem. He submitted those
extra steps in another paper written jointly with his former student Richard
Taylor. Both papers were finally published together in 1995 in Annals of
Mathematics.
<!--more-->

The purpose of peer review in the above process was to make sure Fermat's last
theorem was solved for good. Still imagine Nick Katz and other reviewers
missed the gap in Wiles' proof and allowed publication of the original paper,
but the omission was caught by some other talented mathematician three years
later. Would the mathematics community have continued to say that Fermat's
last theorem was solved, because it was published in a peer reviewed journal,
or would they have reset the status of Fermat's last theorem to 'unsolved'
until Wiles or someone else came up with a proper fix? We presume the second.

\--------------------------------------------------------

The rules are upside down in the PI-land of biology as you can see from the
[response of GTEx to Lior Pachter's GTEx is throwing away 90% of their
data](http://liorpachter.wordpress.com/2013/10/31/response-to-gtex-is-
throwing-away-90-of-their-data/). Hidden in the response, you find this gem -

> Yes, although not as a standalone methodological paper but as part of a
large study where RNAseq data were used to perform eQTL analysis (Montgomery,
Nature 2010). That paper was peer reviewed and includes a 1.5 page description
of the methodology in the methods section and a supplementary figure
(Supplementary Figure 23) describing the methods outline
(http://www.nature.com/nature/journal/v464/n7289/full/nature08903.html).

What does 'that paper was peer reviewed' mean here? The way it typically works
in big science biology is that the authors prepared a giant cocktail of mumbo-
jumbos and submitted it to a glam journal. The journal sent the paper and its
huge supplements to three overworked PIs and gave them very short time to
'review' it. There is little chance those PIs figured out every step and
especially the details of those buried in 45th page of 100 page supplement.
Therefore, Lior Pachter possibly wrote the first real peer review of
FluxCapacitor in his earlier blog post.Throwing 'that paper was peer reviewed'
at him is highly disingenuous.

The rest of the 'response' from GTEx reads like it is written by their
marketing guy. Check this part for example -

>

**Is GTEx LITERALLY throwing away 90% of the data?**

Absolutely not! The GTEx project is not throwing away any data at all. In
fact, it provides all data, in both raw and processed forms, to the scientific
community at dbGAP site (http://www.ncbi.nlm.nih.gov/projects/gap/cgi-
bin/study.cgi?study_id=phs000424.v3.p1) or on the GTEx portal
(http://www.broadinstitute.org/gtex/).

Can't those people read? Nobody accused them of discarding 90% of the data and
the objection was very specifically directed toward FluxCapacitor method.
Pachter showed that it was working at 10% efficiency compared to CuffLinks,
and thus suggested that using FluxCapacitor was equivalent to not using 90% of
data.

> Due to project timelines, we started investigating alternative methods.  Our
current experience with FC is that it scales well and can be used in a
production setting.

Do you see how much importance they put on meeting 'project timelines' and
'productions setting', yet pretend that the 'peer review' was as perfect the
one for Fermat's last theorem?

\----------------------------------------

**What is the solution?**

Maybe it is better, if the biologists and bioinformaticians skip this 'peer
review' step altogether and simply upload their papers at some preprint site,
when ready. That way -

(i) the overworked PIs do not get chased with twenty review requests of the
same paper from various journals,

(ii) the community reviews the paper at its leisure and properly evaluates its
truth content,

(iii) we do not have to hear 'this paper is good, because it is published in
Nature' and instead read all scientific reasons for the work being
appreciated.

Heng Li's BWA-MEM paper is one paper that received quite a bit of such
transparent appraisal from other researchers despite not being published in a
'peer reviewed journal'. The code itself is freely available, and anyone can
evaluate the algorithm and the claims made in the paper without much
difficulty. Moreover, our readers added many questions and comments in the
following two threads, and Heng Li took his time to properly address all
criticisms. Most recent comment was added two days back.

[Mapping God Found Scientifically Dishonest by Anonymous Peer
Reviewers](http://www.homolog.us/blogs/students/2013/05/29/mapping-god-
scientifically-dishonest/)

[Is BWA-MEM as Good as BLASR for Aligning PacBio Reads? Part
1](http://www.homolog.us/blogs/blog/2013/10/23/bwa-mem-blasr-look-pacbios-
newly-released-human-data/)

Readers may also check the following exchange between Aaron Darling and Heng
Li regarding the BWA-MEM paper.

[An open peer review of bwa mem](http://darlinglab.org/open-peer-review-bwa-
mem)

[An informal response to Aaron Darling's open review on the bwa-mem
manuscript](https://github.com/lh3/mem-paper/blob/master/response_to_aaron.md)

If the intended purpose of peer review process were to properly evaluate the
claims made in a paper, we would say that the BWA mem paper is better peer
reviewed than many papers published in so called 'peer reviewed' journals.

