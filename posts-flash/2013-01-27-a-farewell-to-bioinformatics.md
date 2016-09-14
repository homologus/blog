---
title: "'A Farewell to Bioinformatics'"
tags: []
categories:
- blog
---
Readers may take a look at [this reddit thread](http://www.reddit.com/r/bioinf
ormatics/comments/179e9k/a_farewell_to_bioinformatics_since_i_am_about_to/)
containing many good discussions on bioinformatics. The leading article is
very negative about bioinformatics, but it had the good impact of bringing in
valuable comments. Especially, the comments from chilloutdamnit and
chrismiller are quite informative.
<!--more-->

Do our readers agree about this on code optimization?

>

I'm in the field of bioinformatics to improve human health and understand deep
biological questions. I care about reproducibility and accuracy in my code,
but 90% of the time, I could give a rat's ass about performance. I'm trying to
find the answer to a question, and if I can get that answer in a reasonable
amount of time, then the code is good enough. This is especially true when you
consider that 3/4 of the things I do are one-off analyses with code that will
never be used again. (largely because 3/4 of experiments fail - science is
messy and hard like that). If given a choice between dicking around for two
weeks to make my code perfect, or cranking out something that works in 2
hours, I'll pretty much always choose the latter. ("Premature optimization is
the root of all evil (or at least most of it) in programming." --Donald Knuth)

That said, when we do come up with some useful and widely applicable code, we
do our best to optimize it, put it into pipelines with robust testing, and
open-source it, so that the community can use it. If his lab never did that,
they're rapidly falling behind the rest of the field.

\--------------------------------

[Ycombinator thread](http://news.ycombinator.com/item?id=5123022) on the same
topic got even bigger. Their community is more in agreement with Fred, the
frustrated ex-bioinformatician. Here are two sample comments from the thread -

> My experience working as a scientific programmer is this: my colleagues
aren't forthcoming. I could list case after case of failure to document or
communicate crucial details that cost me days, weeks and even months of
effort. But I won't, until I have another job lined up. If I were in the
author's position (I'm in another field), I would insist that my colleagues--
all of them, in whatever field I ended up working, were forthcoming about
their work. This is non-negotiable. Being over-busy is no excuse. (It may be
an excuse for not being forthcoming, but right or wrong, I couldn't care less
--I would not work with such people if I could avoid it, for whatever reason.)

Academia rewards journal publication and does not adequately reward
programming and data collection and analysis, although these are indispensable
activities that can be as difficult and profound as crafting a research paper.
At least the National Science Foundation has done researchers a small favor by
changing the NSF biosketch format in mid-January to better accommodate the
contributions of programmers and "data scientists": the old category
Publications has been replaced with Products.

Naming is important to administrators and bureaucrats. It can be easy to
underestimate the extent to which names matter to them. Now there is a
category under which the contribution of a programmer can be recognized for
the purpose of academic advancement. Previously one had to force-fit
programming under Synergistic Activities or otherwise stretch or violate the
NSF biosketch format. This is a small step, but it does show some
understanding that the increasingly necessary contributions of scientific
programmers ought to be recognized. The alternative is attrition. Like the
author of the article, programmers will go where their accomplishments are
recognized.

Still, reforming old attitudes is like retraining Pavlov's dogs. Scientific
programmers are lumped in with "IT guys." IT as in ITIL: the platitudinous,
highly non-mathematical service as a service as a service Information
Technocracy Indoctrination Library. There is little comprehension that
computer science has specialized. For many academics, scientific programmers
are interchangeable IT guys who do help desk work, system and network
administration, build websites, run GIS analyses, write scientific software
and get Gmail and Google Calendar synchronization running on Blackberries. It
is as if scientists themselves could be satisfied if their colleagues were
hired as "scientists" or "natural philosophers" with no further qualification,
as opposed to "vulcanologist" or "meteorologist" (to a first order of
approximation).

> I have some experience working at a genomics research company and I'll
broadly +1 Fred's experience about the industry, although in less negative
terms. I got out before I got jaded, so my perspective is a bit more "oh,
that's a shame" than his. I really like genetics, bioinformatics, hardware,
deep-science, and all that but the timing and fit wasn't right.

The tools are written by (in my experience) very smart bioinformaticians who
aren't taught much computer science in school (you get a smattering, but
mostly it's biology, math, chemistry, etc.). Ex:

http://catalog.njit.edu/undergraduate/programs/bioinformatic...

http://www.bme.ucsc.edu/bioinformatics/curriculum#LowerDivis...

http://advanced.jhu.edu/academic/biotechnology/ms-in-bioinfo...

The tools themselves are written by smart non-programmers (a very dangerous
combination) and so you get all sorts of unusual conventions that make sense
only to the author or organization that wrote it, anti-patterns that would
make a career programmer cringe, and a design that looks good to no one and is
barely useable.

Then, as he said, they get grants to spend millions of dollars on giant
clusters of computers to manage the data that is stored and queried in a
really inefficient way.

There's really no incentive to make better software because that's not how the
industry gets paid. You get a grant to sequence genome "X". After it's done?
You publish your results and move on. Sure, you carve out a bit for overhead
but most of it goes to new hardware (disk arrays, grid computing, oh my).

I often remarked that if I had enough money, there would be a killing to be
made writing genome software with a proper visual and user experience design,
combined with a deep computer science background. My perfect team would be a
CS person, a geneticist, a UX designer, and a visual designer. Could crank out
a really brilliant full-stack product that would blow away anything else out
there (from sequencing to assembly to annotation and then
cataloging/subsequent search and comparison).

Except, I realized that most folks using this software are in non-profits,
research labs, and universities, so - no, there in fact is not a killing to be
made. No one would buy it.

