---
title: More on GPL Licensing of Bioinformatics Programs
tags: []
categories:
- blog
---
Few days back, we posted on [Software Licenses in Bioinformatics Programs and
Their Legal Implications](http://www.homolog.us/blogs/2012/10/19/software-
licenses-in-bioinformatics-programs-and-their-legal-implications/). In that
thread, readers Dogface Macgee and Joey left thoughtful comments that cleared
up some of our confusion about GPL. We already incorporated Dogface Macgee's
comment in the previous thread. Here is Joey's comment -
<!--more-->

> Just another step past what dogface has said, the grad student has the
copyright. He can release it as GPL, make updates to the code, and sell it for
millions of dollars and never release the code. Only the code originally
released as GPL is considered GPL. If he is hired by a company and wants to
use that in their products, he can. He has to give a different license to the
company, which he absolutely can, as the copyright holder. It does get
trickier when you use other libraries and tools, but its not automatic.

If you hold the copyright, this could make you more valuable as they would
have to hire you or purchase from you another licensing set-up if they wanted
to avoid the GPL.

A detailed analysis must be done, but many GPL libraries can be considered as
a System Library and if you use that then your code does not have to be GPL
from the use of that library(others not so much).

GPL is also a license between the user and the copyright holder, you do not
have to release any of your code publicly, ever. You can sell it and then you
must provide it to them, and they may provide it for free to the world. This
wont work well except for very common systems, as there are millions of GPL
programs out there with no support that no one uses (and no one is charging
for). You can also charge a fee for the source code not exceeding the original
fee of the binaries, however the downstream users may provide it to the world.

Just wanted to clear up some misconceptions. Im not a fan of GPL myself and
will avoid libraries and components(although separate components where you are
only acting on the output are fine and dont gpl-infect). I much prefer BSD but
can see some situations where a GPL code would be preferred.

We researched the 'systems library' concept he mentioned, and believe it is
covered under [GPL linking
exception](http://en.wikipedia.org/wiki/GPL_linking_exception).

>

A GPL linking exception modifies the GNU General Public License (GPL) to
create a new, modified license. Such modified licenses enable software
projects which provide library code, to be "linked to" the programs that use
them, without applying the full terms of the GPL to the using program. Linking
is the technical process of connecting code in a library to the using code, to
produce a single executable file. It is performed either at compile time or
run-time in order to produce functional machine-readable code. There is a
public perception, unsupported by any legal precedent or citation, that
without applying the linking exception, code linked with GPL code may only be
done using a GPL-compatible license.[1] The license of the GNU Classpath
project explicitly includes a statement to that effect.

Many free software libraries which are distributed under the GPL use an
equivalent exception, although the wording of the exception varies. Notable
projects include GNU Guile,[2] the run-time libraries of GNAT,[2] GNU
Classpath [3] and the famous GCC Runtime Library Exception.[4]

Compiler runtime libraries also often use this license, e.g. the libgcc
library in the GNU Compiler Collection uses a very similar linking
exception,[5] as well as all libraries of the Free Pascal project.

In 2007, Sun Microsystems released most of the source code to the class
libraries for the Java SE and Java EE projects under version 2 of the GPL
license plus the Classpath linking exception,[6] and used the same license as
one possible license for their enterprise server GlassFish.[7] and for their
NetBeans Java IDE.[8]

Version 3 of the GNU Lesser General Public License (LGPL)[9] is likewise
constructed as an exception to the GPL.[10]

Please feel free to add what you know about GPL, MIT license and other open-
source options.

P. S. [Here](http://www.gnu.org/licenses/gpl-faq.html) is the master source
that answers every question about GPL. It is the GPL FAQ from GNU.

