---
title: 'Gene Myers at the Pacbio Bioinformatics Workshop - Follow #SMRTBFX in Twitter'
tags: []
categories:
- blog
---
A Pacbio bioinformatics workshop is currently going on at NIST in Maryland,
where Gene Myers ([who is not as smart as David
Haussler](http://www.homolog.us/blogs/blog/2015/06/29/ucscs-david-haussler-
wins-award-through-deceptive-claims-gene-myers-loses/) :) ) is the keynote
speaker. Interested readers are encouraged to follow the [SMRTBFX
hashtag](https://twitter.com/hashtag/SMRTBFX?src=hash) in twitter. The slides
from the talk are posted [here](http://www.homolog.us/blogs/blog/2015/08/27
/slides-from-gene-myers/).
<!--more-->

![CNVmKWNWgAAU7F2](http://www.homolog.us/blogs/wp-
content/uploads/2015/08/CNVmKWNWgAAU7F2-300x225.jpg)

Based on twitter reports, Gene Myers said -

1\. The noise in PacBio reads is basic thermodynamic noise -> almost total
random.

2\. Perfect assembly possible iff: 1) poisson sampling 2) random error 3)
reads longer than repeats.

3\. Longer reads take away some fun on solving repeat problem.

4\. The repeats can be resolved by long reads & leveraging heterogeneity of
repeats. No assembler has reached theoretical limits yet.

5\. The future is here - right out of the box reference genomes now possible

6\. It is easier to share data interfaces than software interfaces. Lets
define interfaces so we can play together -- good idea Gene! Same principle
for the software group at celera

7\. GM talked about "classic time-space trade-off" for sequence alignment.
Using trace points save time with minimul space overhead

7\. Gene Myers' [Dazzler blog](https://dazzlerblog.wordpress.com/) with all
code.

8\. Trace-points scale liberally in both time and space

9\. Trace Point Concept better than bam and sam -- for pacbio reads. We would
need converters to bam and sam for other tools

10\. No evidence aligns to A implies A is bad. Vote for the quality of each A
segment.

11\. It is a statistic to vote or this and it gives information about what the
quality is.

12\. Votes of consensus between B reads (aligned reads) to A read (anchor
read) can be used for intrinsic QV

13\. Perfect (near) is within reach. dazzler DB frameowrk for assembly
pipline. Trace points for intrinsic quality values.

14\. All data needed for assembler is now stored in 2 TB of data.

15\. Uses patching to create uniform quality reads its the artifacts to get a
good string graph.

16\. Scrubbers should remove as little real data as possible while removing
all the artifacts from the data

17\. No real world string graphs look perfect because of insufficient
scrubbing

18\. challenge for DAscrub is incorporating repeat analysis. Avail. For
collaborative use. Not stable enough for wide distribution

19\. DAscrub: assemble @PacBio data without error correction step. Coming
soon.

.......and possibly a snub at the doctor, who is currently running NIH and was
his competitor in the Human Genome Project.

![Capture](http://www.homolog.us/blogs/wp-
content/uploads/2015/08/Capture1-300x39.png)

Thanks to @infoecho and others for covering the workshop for us.

