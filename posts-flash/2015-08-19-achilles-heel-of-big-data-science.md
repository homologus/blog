---
title: Achilles Heel of 'Big Data' Science
tags: []
categories:
- blog
---
The promoters of 'Big Data' science argue that by collecting increasingly
large amount of data and by processing the data with clever algorithms, they
can make fundamental scientific discoveries (or other social contributions).
Many others point out the lack of discoveries compared to what the same people
had been promising for years, to which the 'Big Data' supporters say that they
have not collected enough data yet.
<!--more-->

In this article, I present three rules to show that the basic premise of 'Big
Data' is faulty and explain them with many examples. The rules are-

Rule 1.

> **Quality does not scale, but noise scales.**

Rule 2.

> **The noise can only be reduced by high-quality algorithms.**

Rule 3.

> **Rules 1 and 2 are valid at all scales.**

\--------------------------------

Let me start with the simple example of genome assembly from short reads using
de Bruijn graphs. What happens, when one throws in tons and tons of reads to
get higher coverage? The number of [high-quality k-mers (i.e. those truly
matching the genome) remain the same](https://leanpub.com/NGS-assembly/), but
the number of noisy k-mers scale with more data. As you add more coverage, the
number of noisy k-mers start to overwhelm the system. First thing you see is
that your computer RAM space getting filled, leading to periodic crashes. At
even higher coverage, the de Bruijn graph has all kinds of tips and bubbles
formed in addition to real contigs.

Both problems are solvable, but they need high-quality algorithms.

\--------------------------------

Think carefully about the implication of the last sentence within the context
of Rule 3. Rule 3 says that Rule 1 and 2 apply at all scales. That means they
apply for de Bruijn graph, but they also apply for researchers developing
high-quality algorithms.

Let us say, the government throws in a lot of money to get high-quality
algorithms. What happens? Well, high-quality algorithms reach a plateau, but
noise scales with money. As a result, the space of new bioinformatics tools
look similar to de Bruijn graph at 200x coverage. How to figure out what is
good and what is not? Well, maybe you need high-quality algorithms to figure
out which algorithms are worth using :)

\--------------------------------

I thought about the mentioned rules for months and could not find any way to
get out of the constraints imposed by them. In the meanwhile, the scientific
world keeps marching to the tune of 'Big Data' in all aspects. Every aspect of
it, including ranking papers based on citation (or God forbid - retweets) is
vulnerable. The same goes for automated annotation of public databases based
on existing data. This last point will be the focus of another forthcoming
post.

\----------------------------------------------------------------

Edit.

Stephano Lonardi posted a link to his paper, and believe it or not, I was
looking for the same paper in my directory, while writing this blog post
today, but could not locate it. That is no coincidence, because my initial
thinking six months back was influenced by [his paper posted at
biorxiv](http://biorxiv.org/content/early/2015/01/03/013425). At that time, I
was working on 1000x E. coli data posted by the SPAdes group and made similar
observation in the assembly stats. The explanation (dBG getting more noise)
seemed obvious, but it is also known that SPAdes manages to produce a good
assembly from 1000x data. That observation inspired the rest of the thinking
about need for high-quality algorithm to overcome noise.

You may also realize that throwing more money to solve assembly problem would
not have obtained the high-quality solution, but instead polluted the space
with too much noise (i.e. low-quality algorithm). It was rather Pevzner's work
of over two decades that got us there. That is the essence of Rule 3 in one
human context.

