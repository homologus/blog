---
title: GATK Battle - 2015 Edition
tags: []
categories:
- blog
---
The time for [two minutes hate](http://en.wikipedia.org/wiki/Two_Minutes_Hate)
over GATK is back.
<!--more-->

![Capture0](http://www.homolog.us/blogs/wp-
content/uploads/2015/04/Capture0-300x167.png)

![Capture2](http://www.homolog.us/blogs/wp-
content/uploads/2015/04/Capture2-300x247.png)

Last time, it was due to GATK being licensed by a private company with
contract from Broad Institute (check "[Sanger Dropping Broads GATK after
License Change](http://www.homolog.us/blogs/blog/2012/11/20/sanger-dropping-
broads-gatk-after-license-change/)"). This time, people are upset to see
[Broad Institute running the licensing service
directly](https://www.broadinstitute.org/gatk/about/#licensing).

> Direct licensing and support through Broad

Until now, we have relied on a commercial partner to provide licensing and
premium support services. Starting April 16, 2015, we will be providing
licensing and support directly to commercial entities that will be running the
GATK or MuTect internally or as part of their own hardware offering. Current
licensed users will transition to Broad Institute when their current license
expires. This new model will allow licensed customers better access to the
GATK and MuTect development and support teams, full support for the latest
releases of our tools, and the most up-to-date Best Practice recommendations
that are based on our team's extensive analysis and R&D; work.

The biggest mystery, of course, is why GATK is still in use. BWA-MEM, the most
efficient component of GATK, is available for free (GPL). The remaining
components are written in Java and are supposedly too bulky. Everyone
complains about them. Isn't it time to switch to BALSA from T.-W. Lam's group
and save both (running) time and money? Keeping BWA-MEM and combining with
other components of BALSA would be a viable option as well. Heng Li had other
suggestions mentioned in the following link.

[What Will Replace GATK in the BALSA
Age?](http://www.homolog.us/blogs/blog/2014/04/26/what-will-replace-gatk-in-
the-balsa-age/)

