---
title: Titus Brown's Thoughts on the Assemblathon 2 paper
tags: []
categories:
- blog
---
Titus Brown finished reviewing Assemblathon 2 paper and [wrote an excellent
commentary](http://ivory.idyll.org/blog/thoughts-on-assemblathon-2.html) that
the readers should take a look at. Why do we need to pay attention to Titus
Brown's opinions? It is mainly because he is a rare bioinformatician, whose
group assembled few genome scale (or bigger) sequence libraries, and yet he
does not have his name on the Assemblathon paper. He is not in, mainly because
his group is not associated with any large genome center. So, he can be more
candid about genome assembly factories than almost everyone else around the
world.
<!--more-->

>

...as a field, we have pretended that genome assembly is a reliable exercise
and that the results can be trusted; the Assemblathon 2 paper shows that
that's wrong.

So, my first beef is that we have not done a good job of communicating this
uncertainty.

My second beef is that we have not done a good job of managing this
uncertainty. If there's one group that should be eyeing the Assemblathon 2
paper with concern, it's the sequencing and informatics centers, who are
increasingly trying to be a one-stop shop for genome analysis. The
Assemblathon 2 paper basically points out that you can't trust what they
produce to be what you want, and (from personal experience) I can tell you
that very rarely do sequencing centers put significant thought into your
specific genome: it tends to be a production pipeline using (shock! surprise!)
what they already know how to use, with a minimum of parameter sweeps. When
you connect this to the Assemblathon 2 paper, what you get is a near-certain
statement that your genome assembly is worse -- perhaps considerably worse --
than it could be. But nobody recognizes this explicitly, and our sequencing
centers are paid to produce sequence, not assemblies, much less good
assemblies, so the incentive isn't there to change.

Instead of trying to repost everything he said, let us briefly go over why
biologists seemed to have neglected or underfunded computational people. This
is how the field evolved. During 2000-2006, biologists believed that if
someone gave them high-quality genomes and few web-based tools to pick
primers, etc., they could carry on in their merry old ways. So, the field of
bioinformatics partitioned into two groups - (i) those associated with genome
centers, who worked on sequencing projects, and (ii) everyone else in various
labs. The first group was generally well funded for their computational work
and continued to prosper. Second group included few young kids, who learned
little bit of python or R on the side, and could download and run simple
scripts, if they were asked to. The perception of bioinformatics being easy
was further fed by microarray companies, who all provided simple graphical
tools to find up/down regulated genes.

Advent of next-gen sequencing through a monkey wrench into that nice
arrangement, because it allowed everyone to sequence billions of Gigabases
without any ability to process. Even if the researchers were not interested in
assembling genomes, assembling transcriptome data (RNAseq) required many of
the same skills, and no large assembly factory was interested in assembling
everyone's RNAseq data. Only when a biologist experiences assembly and
annotation, he realizes how screwed up things are, and how much make up the
pretty genome had to wear to look pretty. We have been working with a group of
researchers on a fish genome, and we remember how difficult it was to explain
why we did not have 'THE genome' and 'THE genes', but progressively improving
sets of genes and genome. Also, it took us quite some time to explain that
instead of targeting some published benchmarks for a perfect 'THE genome', we
should check what biological problem we are solving and make sure the assembly
is giving us correct results.

We agree with Titus on the following point as well, and applied similar
thinking, when we picked [Minia as the top assembly contributor of
2012](http://www.homolog.us/blogs/2013/01/10/top-bioinformatics-contributions-
of-2012/) \-

>

We should be making sure that these assemblers can be run quickly, and
efficiently, on any given set of data. This would let us actually run them and
do parameter sweeps, as opposed to now, where you need to have serious
computational infrastructure to run a lot of these assemblers.

Finally, Titus also touched on Fred's rant, [which seemed to have gotten very
negative public comments everywhere](http://www.homolog.us/blogs/2013/01/27/a
-farewell-to-bioinformatics/). We received a nice email from Fred few weeks
back, and would like to share one part that may surprise you.

>

I'm still digging out of the email this generated. Weirdly, the email I
received has been universally positive, except for the one that had nothing
but "Send from my iPad", but I'll be an optimist and assume that was meant
positively as well. Compare that to the comments on the public fora.

It is quite possible that many others hold similar lowly opinion about
bioinformatics practices as Fred, but unlike Titus, are afraid to write
publicly.

