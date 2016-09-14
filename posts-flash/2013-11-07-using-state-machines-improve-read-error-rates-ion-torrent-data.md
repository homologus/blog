---
title: Using State Machines to Improve Read Error Rates in Ion Torrent Data
tags: []
categories:
- blog
---
In twitter and elsewhere, we are noticing renewed interest on Ion Torrent
machines.
<!--more-->

![Capture](http://www.homolog.us/blogs/wp-
content/uploads/2013/11/Capture6-300x99.png)

This comes on the heels of BGI's announcement to get 37 new Proton machines.

[New Announcements from Ion Torrent and Oxford
Nanopore](http://www.homolog.us/blogs/blog/2013/10/23/proton/)

What bioinformatics challenges are posed by IT sequencers? Ideally none,
because the de Bruijn assembly algorithms and BWT-based alignment algorithms
discussed in our commentaries
([here](http://www.homolog.us/blogs/blog/2011/07/28/de-bruijn-graphs-i/) and
[here](http://www.homolog.us/blogs/blog/2011/10/03/finding-us-in-homolog-us/))
should work well. The issue of homolopolymers is often mentioned and readers
may take a look at one interesting bioinformatics paper published recently.

[Using state machines to model the Ion Torrent sequencing process and to
improve read error rates](http://bioinformatics.oxfordjournals.org/content/29/
13/i344.full.pdf+html)

The first author David Golan created a [beautiful
webpage](https://sites.google.com/site/davidgolanshomepage/flowgramfixer)
describing his method in simple language.

![](https://sites.google.com/site/davidgolanshomepage/_/rsrc/1357670108146/flo
wgramfixer/statemachinefigure.png)

> FlowgramFixer is an improved basecaller for the IonTorrent sequencing
platform, which reduces error rates, and generates more uniquely aligned reads
and more high quality reads than the default base calling algorithm
implemented by IonTorrent in TorrentSuite. It is free and open source.

FlowgramFixer was developed by David Golan, Bob Harris and Paul Medvedev.

IIRC, Rayan Chikhi is also working with Paul Medvedev as a post-doc. It is one
of those CS labs, which continues to publish algorithm-rich high-quality
papers on NGS and bioinformatics in general.

