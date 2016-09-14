---
title: Metagenome Biologist Titus Brown Offers New Course on Internet Realities
tags: []
categories:
- blog
---
![Capture](http://www.homolog.us/blogs/wp-
content/uploads/2013/06/Capture4-300x76.png)
<!--more-->

Our call for websites and web-blogs to use piwik analytics to protect privacy
of readers angered Professor Titus Brown of Michigan State University, whose
blog continues to use google analytics with code 'UA-32627666-1'. Since we
have been deemed 'insanely ignorant' (both 'insane' and 'ignorant'), we will
spread little more ignorance in this commentary to see what other superlatives
he has in his vocabulary.

First we will walk you through an update to 'internet reality' by
[W3C](http://en.wikipedia.org/wiki/W3C), which, if you do not know, is an
organization dealing with the internet and not metagenomes. What is W3C up to?
They are planning to introduce a [new HTTP header
field](http://en.wikipedia.org/wiki/Do_Not_Track#cite_note-1).

>

The Do Not Track (DNT) header is the proposed HTTP header field DNT that
requests that a web application disable either its tracking or cross-site user
tracking (the ambiguity remains unresolved) of an individual user. The Do Not
Track header was originally proposed in 2009 by researchers Christopher
Soghoian, Sid Stamm, and Dan Kaminsky. It is currently being standardized by
the W3C.

You can also check [The History of the Do Not Track
Header](http://paranoia.dubfire.net/2011/01/history-of-do-not-track-
header.html) from Christopher Soghoian's blog. Who is against the move by W3C?
It is the 'reasonable voice' cited by Titus Brown (more near the bottom).

Who is pushing for the change? Mostly people and government of Germany (soon
to be declared 'backward' by Titus Brown), where privacy is still important.
The piwik analytics program we use is being used by 13% of German website,
because [it allows](http://en.wikipedia.org/wiki/Piwik) \-

> Privacy Options the ability to anonymize IP addresses, purge tracking data
regularly (but not report data), opt-out support and Do Not Track support. In
Germany, 13% of .de websites use Piwik because of these options.

.......

Though not strictly speaking a feature, Piwik also has the characteristic that
users are the only people who see their own data. This is a by-product of
Piwik being a self-hosted solution. Software as a service solutions (such as
Google Analytics) on the other hand, have full access to the data users
collect.

What does that last part mean? For those simpletons, [conspiracy
fact](http://www.google.com/#q=conspiracy+fact&biw=1166&bih=588) believers,
non-Obama apologists (non-Obots) and other ignorant souls not being trained
about internet in a metagenomics lab in Michigan, here is how the internet
works.

![write-blog](http://www.homolog.us/blogs/wp-content/uploads/2013/06/write-
blog1-300x225.png)

(i) You request a website from your ipad by typing it on the URL window. Say
you type 'http://ivory.idyll.org/blog/'.

(ii) Your computer sends the request to Titus Brown's server sitting somewhere
in Dearborn, Hoboken or maybe Lansing.

![Capture](http://www.homolog.us/blogs/wp-
content/uploads/2013/06/Capture5-300x153.png)

(iii) Titus Brown's server sends a text file back to your server, which your
browser renders into graphical format displaying the very sad news of his
father passing away. We privately sent our condolences to Titus, but here we
will give you one example to show how knowledgeable he was, even though we
never directly interacted with him. Few months back Titus was looking for
other countries to host an internet/email account and we asked why. Titus
explained that it was for his dad, who was concerned about loss of privacy to
US government. How did a physicist figure out months before media? Maybe he
was 'insanely ignorant' like us :)

Getting back to our original topic, you can actually see the text file that
Titus Brown's server sent to your computer. If you right click your mouse to
select 'view page source', your browser will open an window that looks like
the following image:

![Capture2](http://www.homolog.us/blogs/wp-
content/uploads/2013/06/Capture21-300x140.png)

In it, you will find various code blocks such as this one.

`

var _gaq = _gaq || [];

_gaq.push(['_setAccount', 'UA-32627666-1']);

_gaq.push(['_trackPageview']);

(function() {

var ga = document.createElement('script'); ga.type = 'text/javascript';
ga.async = true;

ga.src = ('https:' == document.location.protocol ? 'https://ssl' :
'http://www') + '.google-analytics.com/ga.js';

var s = document.getElementsByTagName('script')[0];
s.parentNode.insertBefore(ga, s);

})();

`

What does it mean? That code block forces your browser to run a program, which
connects to google every time you read his blog. So, Google servers know
instantaneously, when you access his blog and Google will save your IP
address, time, etc. for eternity. In our 'insanely ignorant' understanding, it
is an unnecessary invasion to readers' privacy. Although the readers can
themselves install plug-ins like ghostera, it is far easier for website and
blog authors to install piwik given how easy the process is. Is Titus Brown
trying to claim that google analytics is absolutely necessary, because
universities like Stanford and online journals like PLOS cannot install a
simple analytics program? Piwik can draw pretty charts just like google
analytics, and as an added advantage piwik gives those charts in real time.
Piwik is open source available under GNU GPL, and so you can change the code
in any way you want. In fact, we are surprised that open-source advocates like
Titus Brown (and apparently 'sane' and 'smart' unlike us) did not find it out
before us given how much he lectures everyone on open-source, GPL and freedom
to see source code.

For the sake of completeness, we did check the 'more reasonable' link in Titus
Brown's tweet and found that it was written by someone, whose goal is to
discredit 'Do not track' movement with lies and misinformation.

![Capture](http://www.homolog.us/blogs/wp-
content/uploads/2013/06/Capture6-300x153.png)

The blog contains a 'white paper' from 2011 claiming to explain why 'Do not
track' will not work and here is the best they could come up with.

> Even while some divisions of government are proselytizing for the rapid
adoption of risky and overly simplistic do-not-track mechanisms that are more
akin to sledgehammers than balanced control methodologies, and aimed
particularly at ad personalization networks -- others in government are
pushing hard for vast and comprehensive data retention laws that would require
ISPs and Web services to record and maintain detailed records of virtually all
Web browsing, email, and other activities.

Unlike the care employed in typical major ad personalization networks to
prevent the association of related data in a manner that could be used beyond
the stated purpose of ad presentations, government-mandated data retention
regimes nearly inevitably require that all activity data be directly tied to
individual users in a manner subject to full identification and reporting on
demand of authorities, sometimes even without the requirement of warrants or
other court orders.

In a nutshell, Google cannot stop tracking you, because 'government' (I
presume US government, because the laws are quite opposite in EU and
especially Germany) is forcing Google to track you, and Titus Brown cannot
install piwik or other free, local and open-source analytics program in his
blog, because we are 'insanely ignorant'.

Sorry Titus, we have no option other than giving you an F in this round.

