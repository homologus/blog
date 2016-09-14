---
title: Thoughts on 'Anecdotal Science' by CTB
tags: []
categories:
- blog
---
Few years back, I met a [young scientist](http://ged.msu.edu/) at a sea urchin
retreat meeting in California and asked which cis-regulatory motif prediction
programs their group uses. His reply was something of this sort - 'we try many
different programs, and then empirically verify the motif. If experiments
confirm the result, it does not matter which program the information came
from.' Biologists preached that approach for years in private meetings, public
discussions and especially in selecting papers for high-visibility journals.
As a result, biology and bioinformatics evolved to generate papers of [this
sort](http://ivory.idyll.org/blog/anecdotal-science.html#disqus_thread) \-
<!--more-->

> I'm starting to notice that a lot of bioinformatics is anecdotal.

People publish software that "works for them." But it's not clear what "works"
means -- all to often either the exact parameters or the specific evaluation
procedure is not provided (and yes, there's a double standard here where
experimental methods are considered more important than computational
methods).

The above comment comes from the same young scientist mentioned earlier, but
it is impressive that he changed his earlier opinion about how bioinformatics
should be done and reported based on his experiences. CTB wants all
computational papers to release source codes and parameters so that the
published results can be **easily** reproduced. Is it too late to turn the
tide around? For other thoughtful commentary on the same topic, please check
[Deepak Singh's blog](http://blog.deepaksingh.net/titus-has-a-point/).

We submitted a comment in CTB's blog, but the browser/disqus system ate it. So
let us reproduce it here with some more detail. We are not very keen on the
idea of forcing researchers to publish their source codes for the following
reasons.

i) It is impossible to properly enforce the rule. How much of source code is
enough? For example, if Matlab Corporation starts a research lab, which
publishes a genome assembly paper to demonstrate how cool Matlab is, should we
ask Matlab Inc. to publish the scripts specific to genome assembly or the
entire Matlab source code? The answer may seem easy ('only the genome assembly
script'), but let us present the next example. If BGI publishes a paper
presenting use of SOAPdenovo for metagenome assembly, do they need to open up
the entire SOAPdenovo tree or only the part for metagenome assembly? In the
second case, one may argue that the source code for the entire SOAPdenovo is
necessary to properly understand the code. So, the answer to how much source
code should be opened up can become somewhat subjective.

ii) Speaking of technology papers, if Pacific Bio published a paper on its
cool sequencing approach, the company has room to reveal quite a bit about its
technology, thanks to patent laws. Software ideas cannot be patented, and that
places software developers at a disadvantage. We understand all standard
argument for open-source codes, etc. Did Google Inc. make their money-making
search codes open yet?

iii) To make matters worse, good software programs take months to write and
second to copy. So, asking bioinformaticians to give away source codes of
carefully designed programs is equivalent to asking a experimental lab to send
its post docs to any other lab interested in reproducing its results. We do
not place experimental labs under such constraints. Why do we need to become
more stringent about computational labs?

Overall, we do not see any reason for papers not to carefully articulate all
steps needed for reproducing results. In computer science, the time-tested
process of articulation is called 'algorithm' and computer scientists
painstakingly kept algorithms separate from implementation ('source code'). We
do not understand, why discussing the algorithm in sufficient detail is not
enough to merit publication.

\------------------

Speaking of how experimental biologists treat results derived from
computational biology, we can present an interesting example from our previous
experiences. Eons back, we [developed a computational
algorithm](http://www.pnas.org/content/100/22/12579.full.pdf) to predict
protein functions from protein-protein interaction data. Unlike other similar
papers published in the same era, we did some extra work.

i) We ran the algorithm on available yeast data and predicted functions of
about 80 or so unannotated proteins with high confidence.

ii) The numbers on known proteins was strong enough to let us muster enough
courage to go to [yeast database](http://www.yeastgenome.org/) and mark up
those 80 genes with functions predicted by our program. Not only that, we even
gave the proteins new names based on our predictions. [It was not easy to find
80 three letter previously unused words for naming genes and SGD places very
complicated restrictions. Often we used a name and SGD curators came back to
us few days back saying that the name was taken away by human, mouse,
Arabidopsis, E. coli or Martians. Finally, we resorted to name a few proteins
with the first names of closest family members and that seemed to work.]

iii) Last month, we were checking how the predictions turned out. In almost
all cases checked by us, the predictions turned out to be correct. However,
only a subset of experimental papers cited our work and the rest cited the
original protein-protein interaction study. Given how we highlighted our work
by going to the extent of naming the genes, there is no way an experimental
biologist working on those specific genes can miss our work. Still, biologists
cannot trust computational work, and are more keen to cite original experiment
generating the data, even though the data itself is noisy.

Long story short, culture developed through many years or decades need to be
changed to make computational work more accepted and make papers non-
anecdotal. That will require years of work. What if CTB changes his mind
again?

