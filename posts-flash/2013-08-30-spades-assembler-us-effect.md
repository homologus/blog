---
title: SPAdes Assembler, Python in Bio, US Effect, Return of Lysenko and Other Stories
  of the Day
tags: []
categories:
- blog
---
**SPAdes Assembler**
<!--more-->

SPAdes assembler is starting to get some love from bioinformaticians, [thanks
to its success in GAGE-B](http://www.homolog.us/blogs/blog/2013/05/20/spades-
and-masurca-assemblers-performed-best-in-gage-b-evaluation/). Australian
bioinformatician Torsten Seemann covered it in his blog and explained the
difference between Velvet and SPAdes.

[How Spades differs from
Velvet](http://thegenomefactory.blogspot.com.au/2013/08/how-spades-differs-
from-velvet.html)

> Despite these alternatives, Velvet has still thrived due to it having a
strong user community, and still giving good, usable assemblies. But there is
always room for improvement and new ideas, and I believe an excellent option
for bacterial assemblies currently is SPAdes. It recently ranked very well in
the GAGE-B assessment and in this post I will explain its relationship to
Velvet in broad terms.

Phil Ashton, who writes an informative blog, also covered SPAdes two month's
back.

[Assembly optimisation impact of error correction and a new assembler,
SPAdes](http://bitsandbugs.org/2013/06/28/assembly-optimisation-impact-of-
error-correction-and-a-new-assembler-spades/)

In addition to being a great assembler, the other aspect of SPAdes worth
mentioning is the SPAdes papers. All three of them (main paper, rectangular
graph paper and Son Pham's pathset graph paper) are very informative on the
algorithmic aspects of dBG. Last year we wrote a number of commentaries on
SPAdes, but they are no substitute for going through the papers themselves.

[From de Bruijn Graphs to Rectangle Graphs for Genome
Assembly](http://www.homolog.us/blogs/blog/2012/09/12/from-de-bruijn-graphs-
to-rectangle-graphs-for-genome-assembly/)

[Starting to Understand the SPAdes
Papers](http://www.homolog.us/blogs/blog/2012/09/17/few-thoughts-on-spades-
papers/)

[Rectangular Graph Algorithm](http://www.homolog.us/blogs/blog/2012/10/25
/rectangular-graph-algorithm/)

[Going Through the SPAdes Code (Rectangular
Graph)](http://www.homolog.us/blogs/blog/2012/10/19/going-through-the-spades-
code-rectangular-graph/)

\----------------------------------

**Python for Biologists**

[Link](http://pythonforbiologists.com/index.php/introduction-to-python-for-
biologists/)

> This is the index page for everything to do with the Python for Biologists
course a free introductory programming course for biologists, suitable for
complete beginners. You can scroll down to start reading the course content
right away as a set of web pages. You can also get the course as a free ebook
in PDF format enter your email address to get a copy of the ebook and
exercises (and occasional notifications when the book is updated).

Also check Jason Chin's "[Write A Genome Assembler with blasr and (I)Python](h
ttp://nbviewer.ipython.org/url/files.figshare.com/1009027/Write_An_Assembler.i
pynb)"

> I am not sure it is right thing to do some coding in a vacation. (See this
tweet, not sure if I would agree.) Anyway, before the vacation, I decided to
organize whole bunch of random papers I collected in the last few years in my
laptop. I eventually felt that I should read some of some theoretical papers
about genome assembly again. I grabbed Gene Meyer's paper, and started to
think about the problem about constructing unitigs (high-confident contigs).
Before I tried to read the paper in detail, I just felt maybe that it was
useful to write some quick code to check out what real data looked like. I
started writing some code visualizing the local overlapping and generating the
global overlapping graph. It was pretty straight forward and quite inspiring
from the visualization. The visualization motived me to write more ad-hoc code
in IPython to go beyond generating simple visualization during the vacation. I
started to implement a very simple greedy algorithm to connect the input DNA
fragments. Eventually, I found I can atucally get the whole genome assembly
right!! This Notebook shows the work step by step toward a simple genome
assembler for long read data using IPython and Python.

\------------------------------------

**Return of Lysenko?**

![](http://www.rsrt.org/_cms/wp-content/uploads/2011/06/Adrian-P-Bird-PhD.png)

In a commentary titled [Genome Biology: Not Drowning but
Waving](http://www.sciencedirect.com/science/article/pii/S0092867413010040)
published in Cell, UK scientist Adrian Bird wrote about various unscientific
ideas and inflated claims permeating through biology (h/t: @genologos). Those
are ENCODE, GWAS, long noncoding RNAs expressed in 85% of genome and
epigenetics, and we discussed why those are epitomes of bad science. Dr. Bird
linked epigenetics to Lamarckian evolution and we found that idea thought-
provoking.

> Unlike the longstanding debates about the nature of genes and the concept of
junk DNA, controversy regarding the impact of epigenetics is relatively
recent. Among several current perceptions of epigenetics (Bird, 2007), the
most radical is that epigenetic information can be transmitted across animal
generations. Add to this scenario the widespread assumption that epigenetic
marking is often directed by the environment and we have the essential
ingredients of Lamarckian evolution, or inheritance of acquired
characteristics. An oft-quoted example of intergenerational transmission of an
environmentally determined trait is altered mortality among the descendants of
people who experienced the Swedish famines (Pembrey et al., 2006). But while
it is conceivable that transmission between generations of chemical marks on
the genome underlies this effect, it is dif?cult to exclude the possibility
that effects of the trauma were transmitted culturally across generations who
grew up in familial contact.

Few days back, while learning about Russian history, we reread the story of
[Lysenkoism](http://en.wikipedia.org/wiki/Lysenkoism) built on Lamarckian
evolutionary ideas.

> Lysenkoism (Russian: ?????????????), or Lysenko-Michurinism was the
centralized political control exercised over genetics and agriculture by
Trofim Lysenko and his followers. Lysenko was the director of the Soviet
Union's Lenin All-Union Academy of Agricultural Sciences. Lysenkoism began in
the late 1920s and formally ended in 1964.

Lysenkoism was built on theories of the heritability of acquired
characteristics that Lysenko named "Michurinism".[1] These theories depart
from accepted evolutionary theory and Mendelian inheritance.

Lysenkoism is used metaphorically to describe the manipulation or distortion
of the scientific process as a way to reach a predetermined conclusion as
dictated by an ideological bias, often related to social or political
objectives.

In 1928, Trofim Lysenko, a previously unknown agronomist, claimed to have
developed an agricultural technique, termed vernalization, which tripled or
quadrupled crop yield by exposing wheat seed to high humidity and low
temperature. While cold and moisture exposure are a normal part of the life
cycle of fall-seeded winter cereals, the vernalization technique claimed to
increase yields by increasing the intensity of exposure, in some cases
planting soaked seeds directly into the snow cover of frozen fields. In
reality, the technique was neither new (it had been known since 1854, and was
extensively studied during the previous twenty years), nor did it produce the
yields he promised, although some increase in production did occur.

This part about Lysenkoism is the most interesting. Lysenkoism was established
through mass media and propaganda.

> Isaak Izrailevich Prezent, a main Lysenko theorist, presented Lysenko in
Soviet mass-media as a genius who had developed a new, revolutionary
agricultural technique. In this period, Soviet propaganda often focused on
inspirational stories of peasants who, through their own canny ability and
intelligence, came up with solutions to practical problems. Lysenko's
widespread popularity provided him a platform to denounce theoretical genetics
and to promote his own agricultural practices. He was, in turn, supported by
the Soviet propaganda machine, which overstated his successes and omitted
mention of his failures. This was accompanied by fake experimental data
supporting Lysenkoism from scientists seeking favor and the destruction of
counter-evidence to Lysenko's theories. Instead of performing controlled
experiments, Lysenko claimed that vernalization increased wheat yields by 15%,
solely based upon questionnaires taken of farmers.

Professsor Bird wrote other articles criticizing epigenetics -

[Perceptions of epigenetics](http://neuron.illinois.edu/sites/default/files/U3
_L7_Supplement_PerceptionsOfEpigenetics.pdf)

> Geneticists study the gene; however, for epigeneticists, there is no obvious
epigene. Nevertheless, during the past year, more than 2,500 articles,
numerous scientific meetings and a new journal were devoted to the subject of
epigenetics. It encompasses some of the most exciting contemporary biology and
is portrayed by the popular press as a revolutionary new science an antidote
to the idea that we are hard-wired by our genes. So what is epigenetics?

Other respected biologists like Eric Davidson and Mark Ptashne expressed
similar opinions, and you can find the links in the following commentary
(check epigenetics section).

[Epigenetics in Stem Cells Is It a Significant Paradigm Shift in
Biology?](http://www.homolog.us/blogs/blog/2013/04/30/epigenetics-in-stem-
cells-is-it-a-significant-paradigm-shift-in-biology/)

\-------------------------------------

**US Effect**

That brings us to the fourth part of today's commentary - US effect. It is
mentioned only in a [news article in
Guardian](http://www.theguardian.com/science/2013/aug/26/research-funding-
exaggerates-results), but in no US-based mass media.

> **Research finds 'US effect' exaggerates results in human behaviour
studies**

Pressure on scientists to come up with exciting results could soon spread to
other developed countries, researchers warn

Scientists who study human behaviour are more likely than average to report
exaggerated or eye-catching results if they are based in the United States,
according to an analysis of more than 1,000 research papers in psychiatry and
genetics. This bias could be due to the research culture in the US, authors of
the analysis said, which tends to preferentially reward scientists for the
novelty and immediate impact of a piece of work over the quality or its long-
term contribution to the field.

Daniele Fanelli, University of Edinburgh, one of the authors of the latest
analysis, said that there was intense competition in the US for research funds
and, subsequently, pressure to report novel findings in prestigious, high-
impact scientific journals.

The original study is published in PNAS. John P. A. Ioannidis wrote a number
of other papers on similar theme, and we recommend them all.

[US studies may overestimate effect sizes in softer
research](http://www.pnas.org/content/early/2013/08/21/1302997110)

What do we get, when we combine the core themes of 'US effect' and 'Return of
Lysenko?' ? Funding pressure from the government is forcing researchers to BS
more, and their BS earns more reward in terms of government funding, if they
cover dubious topics such as epigenetics. Are we trying to reach Lysenko
through a different route?

\---------------------------------------

**On Joke Papers, Hoaxes, and Pirates**

[Good commentary by Iddo](http://bytesizebio.net/index.php/2013/08/14/on-joke-
papers-hoaxes-and-pirates/)

> Joke papers have been known to sneak into otherwise serious publications.
Notably, in the Sokal Affair, Alan Sokal, a physicist, published a nonsense
paper in Social Text, a leading journal in cultural studies. After it was
published, Sokal revealed this paper to be a parody, kicking off a culture war
between the editors of Social Text who claimed they accepted the paper on
Sokals authority, and Sokal & others who said that this was exactly the
problem: papers should be subject to review, rather than being accepted on
authority. The Sokal affair highlighted the cultural differences between
certain sections of the social sciences and the natural sciences, specifically
about how academic merit should be established.

Another well-publicized hoax publication occurred when a group of MIT students
wrote SciGEN, a program that generates random computer-science papers. One
such paper was accepted to the WMSCI conference in 2005, in a non peer-
reviewed track. Once the organizers learned theyve been had, they disinvited
the authors, which did not stop them from going to the conference venue
anyway, and holding their own session at the conference hotel.

Speaking of jokes, fictions and non-fictions, here is a quick story. Schools
are starting all over USA and yesterday we attended a short session with our
local elementary school teacher to know what our kids would learn over the
year. She mentioned that she would teach the kids some fictional writing, and
that reminded us of a [Nature
paper](http://www.nature.com/nature/journal/v489/n7414/full/nature11247.html).

> These data enabled us to assign biochemical functions for 80% of the genome,
in particular outside of the well-studied protein-coding regions.

She also mentioned that she would teach non-fictional writing, which reminded
us of an article from The Onion. It described the truth very well, and would
surely pass as non-fiction writing.

[Let Me Explain Why Miley Cyrus VMA Performance Was Our Top Story This
Morning](http://www.theonion.com/articles/let-me-explain-why-miley-cyrus-vma-
performance-was,33632/)

