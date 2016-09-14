---
title: Testing SOAPdenovo2 Prerelease &ndash; V (map and scaff)
tags:
- SOAPdenovo
categories:
- blog
---
We would like to complete our description of SOAPdenovo2 commands and get into
more interesting topics, such as how good the quality of the assembly is.
Before we get there, here are the last two steps of assembly -
<!--more-->

* * *

**'map'**

./SOAPdenovo-63mer-v2.04.3 map -s config_file -g outPG -p 32

The above command maps the reads back on to the assembled contigs. The command
needs at least two parameters - name of the configuration file and prefix for
the graph. In addition, we gave it the number of processors ('-p 32') to speed
up the run. All parameters were explained in our previous commentaries
[here](http://www.homolog.us/blogs/2012/07/04/testing-soapdenovo2-pre-release-
version-part-ii/) and [here](http://www.homolog.us/blogs/2012/07/05/testing-
soapdenovo2-prerelease-iv-building-contigs/).

The map command took several hours to run, and produced four output files.

**outPG.readInGap.gz** \- very large file containing information about the reads that mapped in the gaps between contigs. 

**outPG.readOnContig.gz** \- very large file containing information about the reads that mapped onto gap. 

**outPG.newContigIndex** \- a text file containing some kind of index. 

**outPG.peGrads** \- a tiny file with some kind of statistical information on the mate pair sizes. 

* * *

**'scaff'**

./SOAPdenovo-63mer-v2.04.3 scaff -g outPG -p 32

The above command completed the assembly by utilizing longer mate pair reads
and joining contigs into scaffolds. The process of building up of contigs
('SOAPdenovo contig') did not use mate pairs, because [we did not give that
option in our config file](http://www.homolog.us/blogs/2012/06/27/testing-
soapdenovo2/).

This step took about an hour and produced a number of output files. At this
point, we cared about one and only one file, and its name is shown at the
bottom.

**outPG.asm**, **outPG.bubbleInScaff**,**outPG.contig4asm**, **outPG.contigPosInscaff**

**outPG.gapSeq**, **outPG.links**,**outPG.scaf_gap**, **outPG.scafSeq**, **outPG.scafStatistics**

**outPG.scaf** \- **The final assembly.**

