---
title: Why Homolog.us Avoids Google Analytics, OpenID and Other 'Cool' Silicon Valley
  Products
tags: []
categories:
- blog
---
We do not like you to get spied upon for reading our commentaries, and we
realized that farming out our log in or web tracking system to 'do not evil'
companies would have done exactly that. Yes, it is expensive for us to
maintain our own version of [piwik](http://piwik.org/), but we are ready to go
to that extent to
<!--more-->

![](http://www.zerohedge.com/sites/default/files/images/user5/imageroot/2013/0
6/PRISM%204_0.jpg)

Details [here](http://www.zerohedge.com/news/2013-06-06/meet-prism-us-984xn-
us-governments-internet-espionage-super-operation).

\---------------------

We checked hundreds of university websites, blogs and bioinformatics websites,
and found every single one to go for the easy solution of sending your private
information to spying agencies. Here are few examples -

GMOD - UA-33095045-1

Biostarts - UA-101522-12

seqanswers - UA-2960471-1

Titus Brown - UA-32627666-1

Getting Genetics Done - UA-8298649-1

Openhelix - UA-972186-1

ENSEMBL - yes
(http://uswest.ensembl.org/minified/a7b8ca95be62025e2332583d398555c5.js)

yeast genome database - UA-440742-1

Stanford university - UA-1860414-1

Harvard university - UA-2923555-1

Cornell university - UA-1628162-1

So, if you go from Harvard's webpage to Titus Brown's blog and then to
Biostars, every move of you is trackable by outside agents via google
analytics and backdoor. If that kind of tracking bothers you, please ask those
webmasters to remove google analytics. Installing and maintaining piwik is
very easy.

You can find out whether a website is sending private information to google
and spying agencies by viewing the page source of those web sites and looking
for this block of code -

`

var _gaq = _gaq || [];

_gaq.push(['_setAccount', 'UA-101522-12']);

_gaq.push(['_setDomainName', 'biostars.org']);

_gaq.push(['_trackPageview']);

(function () {

var ga = document.createElement('script');

ga.type = 'text/javascript';

ga.async = true;

ga.src = ('https:' == document.location.protocol ? 'https://ssl' :
'http://www') + '.google-analytics.com/ga.js';

var s = document.getElementsByTagName('script')[0];

s.parentNode.insertBefore(ga, s);

})();

`

