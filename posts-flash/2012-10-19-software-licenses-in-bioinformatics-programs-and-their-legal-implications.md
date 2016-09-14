---
title: Software Licenses in Bioinformatics Programs and Their Legal Implications
tags: []
categories:
- blog
---
We have been going through the codes of various publicly available
bioinformatics programs, and are amazed at the variety of software licenses by
which they are covered. Open source licenses come in many flavors, and each
has its own meaning and long-term consequences. New programmers sometimes do
not think enough before placing an open source license on their codes.
However, some licenses may not be desired by a programmer, or even appropriate
for the kind of code. Let us go through the most popular ones to understand
what they really mean.
<!--more-->

**A. GNU GPL**

[GNU GPL](http://www.gnu.org/licenses/gpl-2.0.html) is the most commonly used
open source license. Many top assembly programs, such as Velvet, Oases and
SPAdes, come with GNU GPL license.

GNU GPL license is also the least understood, because it starts with this
misleading preamble -

> When we speak of free software, we are referring to freedom, not price. Our
General Public Licenses are designed to make sure that you have the freedom to
distribute copies of free software (and charge for this service if you wish),
that you receive source code or can get it if you want it, that you can change
the software or use pieces of it in new free programs; and that you know you
can do these things.

To protect your rights, we need to make restrictions that forbid anyone to
deny you these rights or to ask you to surrender the rights. These
restrictions translate to certain responsibilities for you if you distribute
copies of the software, or if you modify it.

![](http://2.bp.blogspot.com/-Iz6Zq8mO1zo/T0PHHB26drI/AAAAAAAAAFM/owwITApzhpc/
s320/karl-marx-hip.jpg)

Many software programmers feel that GPL takes away their freedom rather than
protecting it. How so?

Let us say that, as a graduate student, you write a cool hash function code
and release it to others under GNU GPL. However, it does not get accepted by
the community due to lack of understanding, existing codes or whatever other
reason.

Four years later, you join a software company and want to increase the
efficiency of their code by using your hash function. After all, if you do not
show off your creation by using it in as many situations as you can, how do
you expect others to acknowledge what you did? However, you find yourself in
this odd situation, where you cannot use the code, because it has been
released under GPL. as per GPL contract, if you use your GPL code in a
proprietary software, the the company must release codes for all its programs.

Why so? Because GPL license requires that all programs compiled together with
a small amount of GPL code has to be publicly released. Not only that, even a
library dynamically linked to code with GPL code has to give out all its
source code. It is a bad license, and nightmare to others. So, the most likely
decision from company managers will be to ask you to stop using your code.

Essentially, by using GPL to release your code, you gave away your freedom.
Even worse, GPL copyrighted the license text. So, you cannot remove parts of
the license that you agree with before releasing your code.

**Correction.** The above description is not entirely correct as reader dogface macgee pointed out. Please check [dual licensing method](http://openlife.cc/onlinebook/dual-licensing-mysql-trolltech-qt) used by MySQL and Qt to release their codes under GPL. 

> MySQL Ab is a Swedish company known for its popular database program, which
is particularly liked for data storage of web pages that run on a Linux
platform. The MySQL database can be downloaded for free from the Internet
under the same GPL licensing system as Linux. Another option is to buy it
under licence for $500. But why would anybody choose to pay 500 bucks for
something they can get for free?

Some people want to pay for it to avoid having to commit themselves to the
terms of Open Source. The General Public Licence (GPL) requires programmers
who use some GPL licensed code or program in any of their software to also
publish their own work under the GPL, source code and all.1 Which is why the
programmers who make closed programs can't use the free Open Source version of
MySQL, but have to pay $500 for a so-called "commercial licence'. These
customers are usually pretty happy with their purchase, because $500 is not a
steep price to pay for a good database product.

However, please remember that you can dual license only the code developed by
you, not the other GPL codes you used in your files. That means, if your code
is not entirely developed by you and needs other GPL libraries to run, you
cannot put it back inside a license. Nonetheless, dual license has become the
most viable method to make money out of GPL codes.

**B. MIT license**

MIT license covers a broad class of licenses, which are all of this form -

[e.g. Trinity]

> Copyright (c) 2011, The Broad Institute, Inc. All rights reserved.

Redistribution and use in source and binary forms, with or without
modification, are permitted provided that the following conditions are met:

Redistributions of source code must retain the above copyright notice, this
list of conditions and the following disclaimer.

Redistributions in binary form must reproduce the above copyright notice, this
list of conditions and the following disclaimer in the documentation and/or
other materials provided with the distribution.

Neither the name of the Broad Institute nor the names of its contributors may
be used to endorse or promote products derived from this software without
specific prior written permission.**

THIS SOFTWARE IS PROVIDED BY THE BROAD INSTITUTE ''AS IS'' AND ANY EXPRESS OR
IMPLIED WARRANTIES, INCLUDING, BUT NOT LIMITED TO,

THE IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE
ARE DISCLAIMED. IN NO EVENT SHALL THE BROAD INSTITUTE BE LIABLE FOR ANY
DIRECT, INDIRECT, INCIDENTAL, SPECIAL, EXEMPLARY, OR CONSEQUENTIAL
DAMAGES(INCLUDING, BUT NOT LIMITED TO,

PROCUREMENT OF SUBSTITUTE GOODS OR SERVICES; LOSS OF USE, DATA, OR PROFITS; OR
BUSINESS INTERRUPTION) HOWEVER CAUSED AND ON ANY THEORY OF LIABILITY, WHETHER
IN CONTRACT, STRICT LIABILITY, OR TORT (INCLUDING NEGLIGENCE OR OTHERWISE)
ARISING IN ANY WAY OUT OF THE USE OF THIS SOFTWARE, EVEN IF ADVISED OF THE
POSSIBILITY OF SUCH DAMAGE.

[e.g. Google sparehash]

> // Copyright (c) 2005, Google Inc.

// All rights reserved.

//

// Redistribution and use in source and binary forms, with or without

// modification, are permitted provided that the following conditions are

// met:

//

// * Redistributions of source code must retain the above copyright

// notice, this list of conditions and the following disclaimer.

// * Redistributions in binary form must reproduce the above

// copyright notice, this list of conditions and the following disclaimer

// in the documentation and/or other materials provided with the

// distribution.

// * Neither the name of Google Inc. nor the names of its

// contributors may be used to endorse or promote products derived from

// this software without specific prior written permission.

//

// THIS SOFTWARE IS PROVIDED BY THE COPYRIGHT HOLDERS AND CONTRIBUTORS

// "AS IS" AND ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT

// LIMITED TO, THE IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR

// A PARTICULAR PURPOSE ARE DISCLAIMED. IN NO EVENT SHALL THE COPYRIGHT

// OWNER OR CONTRIBUTORS BE LIABLE FOR ANY DIRECT, INDIRECT, INCIDENTAL,

// SPECIAL, EXEMPLARY, OR CONSEQUENTIAL DAMAGES (INCLUDING, BUT NOT

// LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS OR SERVICES; LOSS OF USE,

// DATA, OR PROFITS; OR BUSINESS INTERRUPTION) HOWEVER CAUSED AND ON ANY

// THEORY OF LIABILITY, WHETHER IN CONTRACT, STRICT LIABILITY, OR TORT

// (INCLUDING NEGLIGENCE OR OTHERWISE) ARISING IN ANY WAY OUT OF THE USE

// OF THIS SOFTWARE, EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.

Do you see the pattern? They are releasing their codes for public use, but are
not taking away their own freedom or the freedom of others in using the code.
Moreover, the license itself is not copyrighted, and so anyone can change the
license statement to his desire, or at least by putting the name of his own
organization at the top.

**C. GNU LGPL**

GNU Lesser GPL is a step down by GNU after figuring out that MIT license is
liked by programmers. In this form, you still need to release the source code
of any code that uses GPL, but not all library dynamically linked to it.

You can read more about it [here](http://www.gnu.org/licenses/lgpl.html).

**D. Artistic license**

MUMMER comes under [Artistic license](http://opensource.org/licenses/artistic-
license.php) released by OSI, which is a GNU's competing organization. The
license is similar to GPL but with one important difference, [as explained by
a stackoverflow user](http://stackoverflow.com/questions/1699619/artistic-
license-v2-0-vs-gpl-v2-differences) \-

> The biggest difference is that the GPL requires you to distribute source
code if you modify or derive from the code. The Artistic Licence 2.0 does not.

The GPL requires you to ship source code if you make any changes and ship the
binary. This is why is it known as a viral license. Companies have been sued
to force them to release their source code because of the GPL. See Linksys for
one example.

The Artistic License 2.0 does not require code to be redistributed. It is
possible to take code licensed in this way and use it in a propreitary
solution and not have to ship your modifications. All you would need is to
call it something different and give the original author credit. In this way
it is much like the BSD license.

**Non-commercial license**

Some programs (such as the ones released by Conway and Bromage group in
Australia) come under 'non-commercial' license. Please note that non-
commercial license applies to the executable code, and not source code. We do
not touch non-commercial codes, because the meaning of 'commercial use' is not
very clear to us.

\------------------------

**Related question: Can we use any license in our to-be released code?**

The answer is NO. You need to do detailed analysis of where various components
come from. If a single component comes from GPL, your entire code needs to be
released under GPL.

