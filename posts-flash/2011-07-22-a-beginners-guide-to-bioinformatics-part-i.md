---
title: A beginner's guide to bioinformatics - part I
tags:
- introductory
- bioinformatics
categories:
- blog
---
What topics should I study to learn bioinformatics? - I often get asked this
question by biology students and sometimes even biology professors. The answer
depends on what you want to do, but how would someone, who is new to using
computers for biology, know what can be done? To add to our difficulties,
technology is changing so rapidly that even experts do not know what software
tools will remain useful next year.
<!--more-->

Keeping the above complications in mind, I created a general framework to
describe one's abilities in bioinformatics that should be valid even with
changing technologies. Another reason for creating this framework is to fit
our new posts into one or other category for easy description.

From a top level, I prefer to divide the levels of expertise in bioinformatics
into five layers with 5 being the most difficult.

Layer 1 - Using web to analyze biological data

Layer 2 - Ability to install and run new programs

Layer 3 - Writing own scripts for analysis in PERL, python or R

Layer 4 - High level coding in C/C++/Java for implementing existing algorithms
or modifying existing codes for new functionality

Layer 5 - Thinking mathematically, developing own algorithms and implementing
in C/C++/Java

**Layer 1 - Using web to analyze biological data**

By now, almost all biologists are familiar with using the web to run BLAST on
a new sequence at NCBI, or to fold a short sequence online and check whether
it is a miRNA, or to book hotel rooms for a conference. Ok, the third example
is not bioinformatics. I was only checking whether you can tell the
difference, and if you did, you already got an A+ in Layer 1 :)

I was initially reluctant to split this into a different category, because
using the web to find information seems so easy !! However, the main purpose
of separating this is to show respect to the programmers, who develop online
interfaces. Ease of using the web tends to make biologists think that the web
interfaces are easy to develop. So, they allocate $50 on a $1 million grant
for presenting their data, and then get surprised, when their website crashes
within few weeks of publication. In reality, developing high quality
interfaces is very skill intensive, but also has good return in terms of
visibility of one's work. As a rule of thumb, easier an website is to use,
more difficult it is to develop. Skilled web programmers prefer to work for
Facebook or Zynga for $$$ rather than wasting time with researchers, who show
no respect.

**Layer 2 - Ability to install and run new programs**

Usually, most cutting edge programs (Bowtie, Velvet, Trinity, Stampy, etc.) do
not come with an web interface, because the developers neither have time nor
computing resources to provide web services for everyone. Moreover, even the
traditional programs like BLAST or Interpro-scan cannot be run for thousands
of genes through web interfaces, because data-intensive web services cost
mucho dinero. It is like using someone else's kitchen for free to run a full-
service restaurant - never gonna happen. Therefore, sooner or later, each user
will need to learn downloading and running programs to stay on the cutting
edge of biology.

What skills and technologies are required for layer 2? Firstly, you need your
own computer, and what kind of computer to get is a major decision. "Should it
run Windows, Mac or Linux?" "How much RAM should it have?" "How much hard
drive should it have?" "Should we buy one machine or a cluster?" "Should we
just use high-performance computing facility at the university or Amazon
cloud?" Those are all important questions that need to be asked, if one wants
to fully utilize capabilities of next-gen sequencing machines. Let us address
the issue about computers in a later post and restrict ourselves only to
computational skills.

The good news is that most programs these days can be easily installed in
Windows, Mac or Linux. I remember that in earlier day a program developed for
one type of Unix had to be almost rewritten for another Unix variety.

Regarding computational skills for this layer, one needs to learn how to
install and run programs from the command line. These days, people see
computers as pictures, singers or dancing beauties, and not someone speaking
strange short words such as 'ls', 'mv', 'cp', 'rm' that, if misspelled, can
erase your last five years' work in 5 seconds. However, every computer can
still speak those sweet words, if treated nicely. The challenge of layer 2 is
to learn that language of computers.

The best way to master layer 2 is to first get familiar with UNIX or Windows
command line, and then ask for an expert's help in installing and running
various programs. Carefully watch and write down every word he is typing, and
ask for what they mean in details. You will get a hang of it after few rounds
of trial. Apart from learning how to use UNIX, there is no course to take to
master layer 2, because every program is different installation and running.
Just like golf, practice, practice and practice. For help, online forums for
specific programs are very useful resources.

**Layer 3 - Writing own scripts for analysis in PERL, python and R, and being able to use SQL (suggested by 'Molecular Modelling Blog')**

Let us start with an example. A biologist has large volume of expression data
and wants to find expression levels of 300 transcription factors that he
likes. If he had only three genes, he could have cut and pasted the lines.
Cutting and pasting for 300 genes become a bit laborious and time consuming.
As another example, let us say a biologist wants to extract coordinates
7000-8500 from scaffold_1 of a 300M base genome. This task is also technically
possible by loading the genome into a word processor, but it is not the most
desirable method. Asking a highly skilled programmer to do the above task
becomes sub-optimal use of resources, because the skilled programmers tend to
prefer layers 4 or 5 (explained below) for glory.

Learning a bit of PERL or python can do wonders for small tasks described
above and should be part of every biologist's toolbox. R is a statistical
software that plays similar role for statistical analysis of data, when Excel
is no longer feasible. SQL [suggested by 'Molecular Modelling Blog' in
comments] is helpful for storing volumes of data in mySQL or sqlite database
and efficiently querying them. .

The reason I placed this above layer 2 is because layer 3 needs some
conceptual or mathematical thinking in designing the programs and therefore is
not always straightforward. PERL, python and R can do wonders, when applied by
very skilled programmers. For example, the entire gbrowse genome browser is
written in PERL. On the other hand, for scripting languages can also be
applied by beginners to save time on manual tasks.

In not too distant future, Layers 1-3 will be needed by almost every
biologist, whereas layers 4 and 5 will remain the domains of experts.
Therefore, I will cover those two layers in a new post.

