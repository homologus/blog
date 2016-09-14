---
title: 'Pacbio: Why We Stopped Using PacBioToCA and Lived Happily Thereafter '
tags: []
categories:
- blog
---
When we started working on PacBio data one year back, [everyone recommended
PacBioToCA](http://www.homolog.us/blogs/blog/2012/06/19/an-update-on-using-
pacific-bio-sequences-for-genome-assembly/). Pause for a moment to imagine how
summer of 2012 was. Everyone was talking about Illumina, 454, de Bruijn graph,
Velvet assembler and so on, and these 'weird' reads show up from nowhere.
Using an analogy, everyone is talking about pizza and BioMickWatson shows
[five other foods that are like genome
assembly](http://biomickwatson.wordpress.com/2013/07/24/five-other-foods-that-
are-like-genome-assembly/), namely Eton mess, spaghetti Bolognese, Marmite,
'macaroni' cheese and anchovite. The initial impulse is to turn all those into
toppings for pizza to make them attractive.
<!--more-->

![mac-n-cheese pizza](https://encrypted-tbn3.gstatic.com/images?q=tbn:ANd9GcS1
gTQ7jRThEie5CTSLlB1uV2u7dgu_dXw5YoyiIt4jM6TidGWQ)

That is what PacBioToCA does. It turns PacBios into Illuminas and then let you
forget about them. In detail, PacBioToCA painstakingly aligns all Illumina
reads on to the PacBios and then locally assemble the Illumina reads. From
that point onward, you are back to Illumina world. However, the alignment was
incredibly time-consuming. LSC - the same story. It aligns all Illumina reads
on to PacBio using Novoalign, an incredibly slow PacBio-unaware aligner. We
realized that it made more sense to assemble Illumina reads first and then
align them on PacBios.

Over time we learned that any PacBio pipeline not using BLASR is not doing the
analysis right. Mark Chaisson spent a lot of time to turn BLASR into an
incredibly powerful tool. It includes the read-filtering program. It even has
a PacBio read simulator, which, according to Mark, matches experimental data
better than the [published simulator
PBSIM](http://www.homolog.us/blogs/blog/2012/11/05/a-simulator-for-pacbio-
reads/).

The main advantage of BLASR is its knowledge of indels being the primary mode
of error in PacBio reads. So, it is very PacBio-aware, which other aligners
are not.

![Capture](http://www.homolog.us/blogs/wp-
content/uploads/2013/07/Capture16-300x54.png)

\------------------------------------

Edit.

PacBioToCA also got upgraded, which we have not kept pace with. Here are the
latest updates from Michael Schatz and others -

![Capture1](http://www.homolog.us/blogs/wp-
content/uploads/2013/07/Capture17-300x217.png)

Also, Jason Chin mentioned a better approach -

![Capture2](http://www.homolog.us/blogs/wp-
content/uploads/2013/07/Capture23-300x73.png)

The linked presentations are available
[here](http://schatzlab.cshl.edu/presentations/2013-06-18.PBUserMeeting.pdf)
and most possibly Jason is suggesting the following pipeline -

![Capture](http://www.homolog.us/blogs/wp-
content/uploads/2013/07/Capture18-300x246.png)

If you are using Mike Schatz's method, the following twitter discussion may be
of help to you.

> [@mike_schatz](https://twitter.com/mike_schatz)
[@aphillippy](https://twitter.com/aphillippy) Is there any way to run
mummer3/nucmer in multithread mode? I did some search but I can't find related
info.

>

> -- Jason Chin (@infoecho) [July 25,
2013](https://twitter.com/infoecho/statuses/360237828631830529)

![Capture](http://www.homolog.us/blogs/wp-
content/uploads/2013/07/Capture19-262x300.png)

