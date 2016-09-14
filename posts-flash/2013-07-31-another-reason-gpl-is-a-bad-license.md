---
title: Another Reason GPL is a Bad License
tags: []
categories:
- blog
---
![Capture](http://www.homolog.us/blogs/wp-
content/uploads/2013/07/Capture29-300x63.png)
<!--more-->

While the government-funded academic programmers is fully embracing GPL
license, the professional software communities are increasingly rejecting GPL.
As an example, you can click on the popular packages at [this
list](https://packagist.org/explore/) and check their license progression. All
of the GPL-licensed codes were re-released under MIT-license over the last two
years (example:
[swiftmailer](https://packagist.org/packages/swiftmailer/swiftmailer),
[dbal](https://packagist.org/packages/doctrine/dbal)). GPL is dead in the real
software-land. Isn't that puzzling? Unlike academics, these people do not
write code for government money, and often their software programs are what
they earn money from. So, if at all, they have more reason to release code
under GPL than MIT license, and yet they are moving in droves toward MIT-
license !

The reason is simple. GPL license has been disastrous for small software
companies, which are often run by three or four programmers. Their model for
building code is through extensive amount of sharing, whereas the idea of
sharing code is often spurned in academia. As an example, when FPGA
programmers wanted to build better HMMER, [Sean Eddy was threatened and went
to the extent of copyrighting
HMMER](http://selab.janelia.org/people/eddys/blog/?p=127). The linked blog
post shows that the academic mentality is quite against sharing the code with
the purpose of someone else doing better than the original programmer.

Getting back to the original tweet, here is the latest example of why GPL is
not working for real programmers.

[German Court Finds Fantec Responsible For GPL Violation On Third-Party
Code](http://yro.slashdot.org/story/13/07/30/1527231/german-court-finds-
fantec-responsible-for-gpl-violation-on-third-party-code)

> "Are firms responsible for GPL violations on code they receive from third
parties? A German court thinks so. The Regional Court of Hamburg recently
ruled that Fantec, a European media player maker, failed to distribute
'complete corresponding source code' for firmware found in some of its
products. Fantec claims its third-party firmware supplier provided the company
with appropriate source code, which Fantext made available online. But a
hackathon organized by the Free Software Foundation Europe discovered that
this source code was incomplete, and programmer Harald Welte filed suit. He
won. Mark Radcliffe, an IP expert and senior partner at DLA Piper who
specializes in open source licensing issues, has analyzed the caseand argued
that it underscores the need for companies to implement internal GPL
compliance processes. 'Fantec is a reminder that companies should adopt a
formal FOSS use policy which should be integrated into the software
development process,' he writes. 'These standards should include an
understanding of the FOSS management processes of such third-party suppliers.
The development of a network of trusted third-party suppliers is critical part
of any FOSS compliance strategy.'"

Also, the following discussion from the same thread is insightful:

> Actually at the core of the issue here is not really the GPL. At the core is
that they got the code from another company and relied on that company
adhering to the license.

Basically the ruling says that when you got the code from a third party, you
cannot rely on the third party acting correctly when determining whether your
use of the code complies with the license. If the third party violated the
license (in this case, by not providing the complete source code), it doesn't
protect you from the responsibility of checking the correct licensing yourself
when redistributing the code.

That it was about GPL code is only tangential to the issue (although it's
almost certainly the reason why it ended up on Slashdot).

Basically the scheme is the following: A gives code to B under a given
license. B then gives the code to C in a way that violates A's license. C
relies on B having followed A's license and figures out that redistribution in
a certain way would not violate A's license. However since B's analysis rests
on the false assumption that B complied, it turns out that C's redistribution
of the code also violates A's license. But with a closer inspection, C could
have found out that B didn't comply. The court ruling now says that C is
responsible for violating the license.

Here A is whoever owns the copyright for the code in question, B is Fantec's
firmware supplier, C is Fantec, the license is the GPL, and the violation is
not distributing the complete corresponding source code.

