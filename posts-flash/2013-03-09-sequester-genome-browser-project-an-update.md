---
title: Sequester Genome Browser Project - An Update
tags: []
categories:
- blog
---
Weekends are here and we are back working on the [genome browser project that
is sure to fail](http://www.homolog.us/blogs/2013/03/03/sequester-special-
announcing-a-new-genome-browser-project/). We will write detailed notes on our
thoughts as we go along. That way you can tell your children and
grandchildren, why starting another genome browser project is a stupid idea :)
<!--more-->

Our goals and expectations are very modest at this point. We like the client
side to use HTML5-rendering with AJAXified data import from server side. The
program should self-install out of the box. We plan to release it under MIT-
type license so that anyone can continue to develop it further. Lastly, we
like its development to continue without any support from government grants.

Many thanks to Istvan for pointing us to [chromozoom](http://chromozoom.org/).
It is a beautiful browser. When we saw it, we were nearly ready to abandon our
efforts. We thought we would borrow the client side (HTML+Javascript), add our
server-side modules and get done in days. Then we found out -

> ChromoZoom is free for academic, nonprofit, and personal use. The source
code is licensed under the GNU Affero General Public License v3.....ChromoZoom
is not free for commercial use. For commercial licensing, please contact the
Roth laboratory.

We do not understand the insanity of these academics. The code of chromozoom
is littered with MIT-licensed functions and libraries (jQuery UI, Tokyo
Tyrant, underscore.js, TipTip, ImageMagick, LodePNG and many others). JQuery
UI, among them, is essential for development of the code. Why take a bunch of
open-license (MIT) libraries, make some improvement and lock up the product
from further development? GPL used to be cool some time in the past but not
any more. None of the modern frameworks and libraries in the computer world
come under GPL.

We are also wondering whether author of Chromozoom was the same Theodore Pak
[mentioned here](http://www.thecrimson.com/article/2008/1/9/student-caught-
making-fake-ids-a/). It is puzzling why Harvard was so busy catching minor
infractions, when [real crooks](http://mathbabe.org/2012/03/11/why-larry-
summers-lost-the-presidency-of-harvard/) continued to do [bigger damage to
their institution](http://www.bloomberg.com/apps/news?pid=newsarchive&sid=aHQ2
Xh55jI.Q).

Distractions aside, Chromozoom is beautiful, and we hope to reproduce its
functionality. The main program is a 3000 line Javascript file with three
JQuery UI widgets. The functions are
[here](http://homolog.us/wiki1/index.php?title=Chromozoom) and we do not know
how long it will take us to produce something as good.

Another beautiful HTML5 program is Sebastien's Ray Cloud Browser. It is more a
de Bruijn browser than genome browser, but a designer can get inspiration by
going through his code. His code is GPL-licensed, but we have no complaint,
because he developed it fully without using any external library.

Compare the above two programs with Gbrowse, which is the biggest piece of
garbage being used by bioinformaticians today. PERL-CGI was cool in 1997, but
how many internet companies still use PERL? [Here is the
number](http://trends.builtwith.com/framework/Perl), and [here is number for
PHP](http://trends.builtwith.com/framework/PHP). Even those companies using
PERL for web-server moved on to frameworks like Catalyst, Dancer or
Microlicious. Without government-backing, Growse would not have survived, and
every additional year of support for it takes us back, not forward. Jbrowse is
much better with its [dojo-based client side](http://dojo-
toolkit.33424.n3.nabble.com/jQuery-and-the-long-term-viability-of-Dojo-
td3952249.html), but on the server side, it is hostage to the same backdated
PERL modules as GBrowse.

Chromozoom, in contrast, uses Jim Kent's programs on the server side. From
cursory reading, it seems to us that only the UCSC browser has restrictive
licenses, whereas the other C codes by Jim Kent can be developed freely.

To summarize, we did not make any progress today apart from learning what
others did in their genome browser projects.

