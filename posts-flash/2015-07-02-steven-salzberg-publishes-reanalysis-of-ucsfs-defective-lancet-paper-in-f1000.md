---
title: Steven Salzberg Publishes Reanalysis of UCSF's Defective Lancet Paper in F1000
tags: []
categories:
- blog
---
After [Yoav Gilad's reanalysis of mouse ENCODE
data](http://f1000research.com/articles/4-121/v1), respected computational
biologist [Steven Salzberg took the F1000
route](http://f1000research.com/articles/4-180/v1) to critically re-examine
the claims of another high-profile paper.
<!--more-->

![download](http://www.homolog.us/blogs/wp-
content/uploads/2015/07/download.jpg)

Over the last few years, bio-medical journals have seen severe outbreak of
high-profile papers of poor quality. Cleaning up the mess through the same
exclusive journals is extremely difficult (check the experiences of [Dan
Graur](http://judgestarling.tumblr.com/post/47585203217/sean-eddy-knows-on-
which-side-the-bread-is) or [Lior
Pachter](https://liorpachter.wordpress.com/2014/02/12/why-i-read-the-network-
nonsense-papers/)), but thanks to alternate publishing venues, there is
finally some hope.

Today's paper under fire is about the [recent enterovirus D68 outbreak that
caused 'mystery paralysis' and polio-like
symptoms](http://www.washingtonpost.com/news/to-your-health/wp/2015/03/30
/link-found-between-children-with-paralysis-and-polio-like-strain-of-
enterovirus-d68-study-says/). The authors claimed to have found ([A novel
outbreak enterovirus D68 strain associated with acute flaccid myelitis cases
in the United States from 2012-2014: a retrospective cohort
study](http://www.ncbi.nlm.nih.gov/pubmed/25837569)) through metagenomic
sequencing -

![PhotoHandler](http://www.homolog.us/blogs/wp-
content/uploads/2015/07/PhotoHandler.jpg)

> 48 patients were included: 25 with acute flaccid myelitis, two with
enterovirus-associated encephalitis, five with enterovirus-D68-associated
upper respiratory illness, and 16 with aseptic meningitis or encephalitis who
tested positive for enterovirus. Enterovirus D68 was detected in respiratory
secretions from seven (64%) of 11 patients comprising two temporally and
geographically linked acute flaccid myelitis clusters at the height of the
2014 outbreak, and from 12 (48%) of 25 patients with acute flaccid myelitis
overall. Phylogenetic analysis revealed that all enterovirus D68 sequences
associated with acute flaccid myelitis grouped into a clade B1 strain that
emerged in 2010. Of six coding polymorphisms in the clade B1 enterovirus D68
polyprotein, five were present in neuropathogenic poliovirus or enterovirus
D70, or both. One child with acute flaccid myelitis and a sibling with only
upper respiratory illness were both infected by identical enterovirus D68
strains. Enterovirus D68 viraemia was identified in a child experiencing acute
neurological progression of his paralytic illness. Deep metagenomic sequencing
of cerebrospinal fluid from 14 patients with acute flaccid myelitis did not
reveal evidence of an alternative infectious cause to enterovirus D68.

Salzberg found several defects in their analysis. The authors did not use any
standard bioinformatics program and instead reinvented their version of square
wheel, which they [published as a separate bioinformatics
paper](http://genome.cshlp.org/content/early/2014/05/16/gr.171934.113).
Unfortunately, those great programs failed to find out that two patients had
other major bacterial infections (Haemophilus influenzae and severe
Staphylococcus aureus). Moreover, the authors did not remove human DNA from
patients' data before public submission, as they claimed to have done likely
to protect patients' privacy. The full abstract of Salzberg is shown below -

[Re-analysis of metagenomic sequences from acute flaccid myelitis patients
reveals alternatives to enterovirus D68
infection](http://f1000research.com/articles/4-180/v1)

> Metagenomic sequence data can be used to detect the presence of infectious
viruses and bacteria, but normal microbial flora make this process
challenging. We re-analyzed metagenomic RNA sequence data collected during a
recent outbreak of acute flaccid myelitis (AFM), caused in some cases by
infection with enterovirus D68. We found that among the patients whose
symptoms were previously attributed to enterovirus D68, one patient had clear
evidence of infection with Haemophilus influenzae, and a second patient had a
severe Staphylococcus aureus infection caused by a methicillin-resistant
strain. Neither of these bacteria were identified in the original study. These
observations may have relevance in cases that present with flaccid paralysis
because bacterial infections, co-infections or post-infection immune responses
may trigger pathogenic processes that may present as poliomyelitis-like
syndromes and may mimic AFM. A separate finding was that large numbers of
human sequences were present in each of the publicly released samples,
although the original study reported that human sequences had been removed
before deposition.

Thankfully, the main claim of the original paper is still valid as Dr.
Salzberg pointed out in a private email.

> I should add that the main finding of Greninger et al. is not really in
doubt - their primary analysis showed that the 2014 strain of enterovirus D68
formed a new clade. But the secondary analyses included some surprising flaws.

\--------------------------------

Edit.

1\. Omics!Omics! blog wrote -

[Leaky clinical metagenomics pipelines are a very serious
issue](http://omicsomics.blogspot.com/2015/07/leaky-clinical-metagenomics-
pipelines.html)

\--------------------------------

2\. Charles Chiu, the senior author of UCSF paper, posted a response on his
website signed by three authors (incl. him). I am quoting it here, but please
feel free to discuss at the F1000 site.

[http://chiulab.ucsf.edu/EV-D68-response.docx](http://chiulab.ucsf.edu/EV-D68-
response.docx )

> This manuscript raises two main criticisms of our paper in their re-
analysis. Here we directly address the 2 main points:

1\. The authors claim that bacterial reads were seen in the nasopharyngeal /
oropharygneal swab (NP/OP) metagenomic data that were "missed" in the original
study. They were able to assemble two genomes, from Haemophilus influenzae and
methicillin-resistant Staphylococcus aureus. We would like to highlight that
these reads and bacteria were not missed but instead we did not discuss the
bacterial/fungal portion of the NP/OP swabs in the manuscript due to
difficulties in clinical interpretation.

As quoted from the supplementary section of our manuscript published in Lancet
Infectious Diseases, with our emphasis in underline:

Lancet ID Supplementary Material: NGS libraries constructed from NP/OP samples
were treated with DNase following nucleic acid extraction to reduce background
from the human host and bacterial flora. As this protocol reduces sensitivity
of detection and speciation for non-viral microbes (i.e. bacteria, fungi, and
parasites), only viral sequences are shown for the NP/OP samples. The ability
to detect DNA viruses is also impacted by the use of DNAse and we cannot
exclude the possibility that our data is biased by reduced sensitivity for
detection of DNA viruses.

a) The authors also state that we "did not report finding any bacterial reads
from this sample" but that does not mean that we did not detect any bacterial
reads. In fact, we detected both the Haemophilus influenzae and methicillin-
resistant Staphylococcus aureus reported by the authors:

The number of bacterial reads found in all metagenomic samples analyzed is
shown in Supplementary Table 3, Column N. Bacterial reads for the two samples
in question are listed as US/CA/09-871: 5,614,487 bacterial reads and
US/CA/12-5837: 28,676,383 bacterial reads.

In the main text we also state that the purpose of metagenomic NGS on NP/OP
samples was to "to aid in the recovery of enterovirus D68 genome sequences and
detect potential co-infections from other viruses".

b) In addition, although we reported the presence of bacterial reads in the
NP/OP data, detected using SURPI/SNAP, we did not discuss this in the paper
due to a number of reasons:

Our focus on looking for CSF (bacterial viral fungal and parasite) pathogens
in the setting of AFM our clinical perspective that the presence of bacterial
reads in NP/OP swabs from children most often reflect colonization / carriage
and not infection (see http://www.biomedcentral.com/1471-2180/10/59,
http://www.ncbi.nlm.nih.gov/pubmed/15999003,
http://www.ncbi.nlm.nih.gov/pmc/articles/PMC3962756/,
http://www.ncbi.nlm.nih.gov/pubmed/12394812, etc. for papers on nasal carriage
of Staphylococcus and Haemophilus in healthy children)

our treatment of the nucleic acid extracts with DNase to help reduce host
background, which would bias accurate metagenomic interpretation and the
accurate counting of bacterial and fungal reads since this procedure degrades
bacterial / fungal genomic DNA due to high levels of respiratory tract
colonization, NP/OP samples nearly always contain bacterial sequences that
will constitute the majority of the non-human reads and beyond reporting read
numbers, we did not comment on this in the paper.

c) Of note, the sample in question with Haemophilus influenzae (US/CA/09-871)
came from a 2009 case of upper respiratory infection alone. This subject did
not have either encephalitis or acute flaccid myelitis (Table 2 and results in
Greninger et al.). The statements in the manuscript that "This patient was
reported as having encephalitis and severe respiratory illness..." and "the
sequence evidence here suggests that the patient might have had complications
from H. influenzae-associated encephalitis or encephalomyelitis..." as well as
the title of the manuscript are therefore incorrect.

2\. The authors point out that there are residual human reads in the deposited
data.

We acknowledge that we have been using SNAP, which is a global aligner, to
extract out human reads for our SRA submissions. This algorithm will miss
human reads because of low-complexity sequences at the ends, residual
adapters, etc. We agree that we probably should have used a local aligner such
as BLASTn at a low threshold level to more completely extract out human reads,
or a k-mer approach such as Kraken. We appreciate the authors point on the
importance of clearing human sequences from metagenomic data and will plan on
resubmitting this more completely filtered data to the SRA in the near future.

The re-analysis presented here gives the erroneous impression that bacterial
colonization has a strong association with the devastating acute flaccid
myelitis (AFM) syndrome seen in our patients. As we note above, Haemophilus
influenzae was found in a control patient with no neurological symptoms, and
is thus not relevant to AFM. While MRSA colonization may possibly be a factor
in AFM, it is extremely unlikely given its detection is a single case and the
fact that MRSA nasal carriage in healthy children is well-described. We should
also point out that bacterial cultures of cerebrospinal fluid (CSF) from all
of the patients in the study were negative and that metagenomic next-
generation sequencing did not reveal any evidence of bacterial infection in
the central nervous system (CNS).

![Capture](http://www.homolog.us/blogs/wp-content/uploads/2015/07/Capture-
300x127.png)

