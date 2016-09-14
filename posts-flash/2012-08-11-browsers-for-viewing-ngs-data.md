---
title: Browsers for Viewing NGS Data
tags: []
categories:
- blog
---
We have been searching for a good browser to view our NGS data. So far we were
using IGV, but we thought it would be nice to check what else is out there.
<!--more-->

The query started with two large lists of available browsers -

(i) Table 1 of [recently published GenomeView
paper](http://www.ncbi.nlm.nih.gov/pmc/articles/PMC3258165/),

(ii) an informative [2010
thread](http://seqanswers.com/forums/showthread.php?t=3904) from SEQanswers
forum.

If you know how the internet works, you will understand that the viewers fall
in two categories -

(i) those that make your own computer crash,

(ii) those that make your browser fall asleep.

Jokes aside, in case of (i), you will download the program into your own
computer and run it. IGV fits the description. With the second set of
browsers, remote servers run the calculations, render images, and send them
back to you. Gbrowse is a good example.

**Kind of browsers to avoid at any cost** \- 

[Correction: The following information is incorrect and is about VISTA is
based on an old and obsolete copy of the program. Latest program is [freely
available from LBNL website](http://pipeline.lbl.gov/software.shtml). Also
check [Dr. Dubchak's comment posted
here](http://www.homolog.us/blogs/2013/03/12/vista-genome-browser-from-inna-
dubchaks-group/) and in the comment section for latest information.]

VISTA+AVID from [Inna Dubchak](http://www.jgi.doe.gov/whoweare/dubchak.html)'s
group at JGI.

Why? [Here](http://genome.lbl.gov/vista/mvista/download.shtml) is the answer.
Our blog does not belong to any university. Neither are we officially
registered as non-profit. So, we are 'commercial users'. There is absolutely
no reason to pay $10,000 for a browser to a group of parasites, who got paid
by Federal Government to develop it. Especially when the 'updates and support'
section promises no bug fixes or support, and you will have to pay close to
full price for any future release.

**Browser-based viewers**

We really wanted to find a Javascript+HTML5-based browser that runs as
smoothly as google maps (AJAX is the technical term), and with server side
running in PHP or ruby. Is that too much to ask for in 2012?

Here is what we found.

[Anno-J](http://www.annoj.org/)

It is possibly the closest to what we like to see, but the licensing agreement
seemed a bit complex - "Anno-J is available under a Creative Commons by-nc-sa
3.0 license, although commercial use is permitted if permission from the
author is first obtained." Still that is far better than $10,000 charged by
highway robbers mentioned earlier (and below). We knew J. Tonti-Filippini
through a friend, and he seemed like a reasonable person.

[tbrowse](http://code.google.com/p/tbrowse/) \- nice start, but it is
relatively new and maintained by only one person.

[Jbrowse](http://jbrowse.org/) \- nice AJAX-based browser, but it needs
Bioperl to run. Even though we can speak perl well, having perl in our web-
server is not an exciting idea.

[Gbrowse](http://gmod.org/wiki/GBrowse) \- Linconl Stein's famous browser that
every other genomic website loves. It is open source and AJAXified, but the
GUI is not as smooth as Google map. Moreover, it is another bioperl-based
browser.

[UCSC](http://genome.ucsc.edu/) It is highly recommended by SEQanswer users,
but the browser comes with [a licensing
agreement](http://genome.ucsc.edu/license/gblicense.pdf) that can compete with
its sister organization UC Berkeley in stupidity. Do we have to restrict our
blog-viewership to 3 to fit their 'small business' requirement?

[Ensemble ](http://www.ensembl.org/index.html) \- Is it possible to have the
Ensembl browser without installing the entire Ensembl tree? Somebody please
help us.

[CoGe](http://genomevolution.org/CoGe/) \- Couldn't even figure out how to
download their Browser based on their website.

So, after checking the entire landscape, we picked two - AnnoJ, if licence
allows and gbrowse otherwise. Sad, isn't it?

**Stand-alone Browsers**

Why would one need stand alone browsers? They are very helpful, if you are in
China behind slow internet connection. It is easier to get data from a server,
which gets rendered in your computer than large images.

The list of stand-alone browsers is very big, and almost always the programs
are JAVA-based. We will only stick to six of our choice. In almost all cases,
the licensing scenario is much more friendly than web-based ones of previous
section.

[GenomeView](http://genomeview.org/)

The browser comes from a <del>Dutch</del> Belgian group, but is now being
maintained by Broad Institute. This is at the top of our list for reasons we
cannot explain. Are we showing the symptoms of falling in love? Will it be
followed by a nasty heart break soon?

[Artemis](http://www.sanger.ac.uk/Software/Artemis/)

Comes from Sanger. We have not tried it, but others rated it as good.

[IGV](http://www.broadinstitute.org/igv/)

A very popular browser from Broad institute.

[IGB](http://igb.bioviz.org/download.shtml)

A good browser originally maintained by Affymetrix, but is not being
maintained at an university.

We are not very familiar with the following two browsers, but we like them
based on the descriptions in other places.

[Savant](http://genomesavant.com/)

[Tablet](http://bioinf.scri.ac.uk/tablet/)

[GenomeView paper](http://www.ncbi.nlm.nih.gov/pmc/articles/PMC3258165/) has
nice comparison of the above browsers that you may find helpful. We are
testing the above six starting with GenomeView and IGB. If you like any other
one, please list in the comment section.

