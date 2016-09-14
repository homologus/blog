---
title: Revisiting Fred's Viral "A Farewell to Bioinformatics" One Year Later
tags: []
categories:
- blog
---
Anyone remembers Fred? About a year back, his [March 2012 commentary titled "A
Farewell to Bioinformatics"](http://madhadron.com/posts/2012-03-26-a-farewell-
to-bioinformatics.html) went viral, when [someone posted it on Reddit](http://
www.reddit.com/r/programming/comments/184t5k/a_farewell_to_bioinformatics_fred
_ross/). The link was also posted in [Hacker
news](https://news.ycombinator.com/item?id=5123022), Biostars and
[insignificant places like
homolog.us](http://www.homolog.us/blogs/blog/2013/01/27/a-farewell-to-
bioinformatics/). Fred started to receive hate mails and [called the negative
reaction at reddit "group monkey dance"](http://madhadron.com/posts/2013-01-29
-public-comments-considered-harmful.html).
<!--more-->

![Capture0](http://www.homolog.us/blogs/wp-
content/uploads/2014/02/Capture01.png)

![Capture7](http://www.homolog.us/blogs/wp-
content/uploads/2014/02/Capture71-300x78.png)

After seeing that kind of negative reaction, we sensed that he might have said
something right. That prompted us to go through his other blog posts and they
appeared to be written intelligently ([all links
here](http://www.homolog.us/blogs/blog/2013/01/28/index-to-entire-set-of-
freds-rants/)). Since then, we maintained email contact, and over the year
Fred also privately alerted us about Barabasi's network papers being mostly
junk.

Now that one year has passed and leading mathematicians like Lior Pachter
decided to publicly challenge bioinformatics big-shots, it may be time to
revisit Fred's parting comments. We thought through many of his points over
the year and came to agree with him. For example, we realized that trying to
cure diseases using bigger and bigger SNP association studies were wasteful
([check ecodevoevo blog for daily update on why
so](http://ecodevoevo.blogspot.com/)), came to appreciate the widsom of Carl
Woese [through this paper](http://www.homolog.us/blogs/blog/2014/01/17
/evomics-conference-paper-carl-woese/) and encountered a few molecular
biologists, who were not shy to "tell the programmers (us) the actual quality
of the results".

Here is his full post from two years back.

>

I'm leaving bioinformatics to go work at a software company with more
technically ept people and for a lot more money. This seems like an opportune
time to set forth my accumulated wisdom and thoughts on bioinformatics.

My attitude towards the subject after all my work in it can probably be best
summarized thus: "Fuck you, bioinformatics. Eat shit and die."

Bioinformatics is an attempt to make molecular biology relevant to reality.
All the molecular biologists, devoid of skills beyond those of a laboratory
technician, cried out for the mathematicians and programmers to magically
extract science from their mountain of shitty results.

And so the programmers descended and built giant databases where huge numbers
of shitty results could be searched quickly. They wrote algorithms to organize
shitty results into trees and make pretty graphs of them, and the molecular
biologists carefully avoided telling the programmers the actual quality of the
results. When it became obvious to everyone involved that a class of results
was worthless, such as microarray data, there was a rush of handwaving about
"not really quantitative, but we can draw qualitative conclusions" followed by
a hasty switch to a new technique that had not yet been proved worthless.

And the databases grew, and everyone annotated their data by searching the
databases, then submitted in turn. No one seems to have pointed out that this
makes your database a reflection of your database, not a reflection of
reality. Pull out an annotation in GenBank today and it's not very long odds
that it's completely wrong.

Compare this with the most important result obtained by sequencing to date:
Woese et al's discovery of the archaea. (Did you think I was going to say the
human genome? Fuck off. That was a monument to the vanity of that god-
bobbering asshole Francis Collins, not a science project.) They didn't
sequence whole genomes, or even whole genes. They sequenced a small region of
the 16S rRNA, and it was chosen after pilot experiments and careful thought.
The conclusions didn't require giant computers, and they didn't require
precise counting of the number of templates. They knew the limitations of
their tools.

Then came clinical identification, done in combination with other assays,
where a judicious bit of sequencing could resolve many ambiguities. Similarly,
small scale sequencing has been an incredible boon to epidemiology. Indeed,
its primary scientific use is in ecology. But how many molecular biologists do
you know who know anything about ecology? I can count the ones I know on one
hand.

And sequencing outside of ecology? Irene Pepperberg's work with Alex the
parrot dwarfs the scientific contributions of all other sequencing to date put
together.

This all seems an inauspicious beginning for a field. Anything so worthless
should quickly shrivel up and die, right? Well, intentionally or not,
bioinformatics found a way to survive: obfuscation. By making the tools
unusable, by inventing file format after file format, by seeking out the most
brittle techniques and the slowest languages, by not publishing their
algorithms and making their results impossible to replicate, the field managed
to reduce its productivity by at least 90%, probably closer to 99%. Thus the
thread of failures can be stretched out from years to decades, hidden by the
cloak of incompetence.

And the rhetoric! The call for computational capacity, most of which is
wasted! There are only two computationally difficult problems in
bioinformatics, sequence alignment and phylogenetic tree construction. Most
people would spend a few minutes thinking about what was really important
before feeding data to an NP complete algorithm. I ran a full set of
alignments last night using the exact algorithms, not heuristic
approximations, in a virtual machine on my underpowered laptop yesterday
afternoon, so we're not talking about truly hard problems. But no, the
software is written to be inefficient, to use memory poorly, and the cry goes
up for bigger, faster machines! When the machines are procured, even larger
hunks of data are indiscriminately shoved through black box implementations of
algorithms in hopes that meaning will emerge on the far side. It never does,
but maybe with a bigger machine...

Fortunately for you, no one takes me seriously. The funding of molecular
biology and bioinformatics is safe, protected by a wall of inbreeding,
pointless jargon, and lies. So you all can rot in your computational shit
heap. I'm gone.

