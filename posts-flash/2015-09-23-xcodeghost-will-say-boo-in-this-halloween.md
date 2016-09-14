---
title: XcodeGhost Will Say Boo in this Halloween
tags: []
categories:
- blog
---
![240px-Jack-o'-Lantern_2003-10-31](http://www.homolog.us/blogs/wp-
content/uploads/2015/09/240px-Jack-o-Lantern_2003-10-31.jpg)
<!--more-->

These days, a large number of people live in the virtual world communicating
with virtual friends. What better way to scare them than to introduce a
virtual ghost? :) Looks like such a ghost has appeared in the Iphone world and
is appropriately named XcodeGhost (h/t: Ruibang). Here is what happened.

Most Iphone users download their apps (binary programs) from the Apple App
store, and the developers create those apps using [Xcode development software
provided by Apple](https://en.wikipedia.org/wiki/Xcode). Even with a good
internet connection, downloading Xcode development software takes over 15
minutes in USA, and possibly longer in other countries. Therefore, some
developers in China used a local mirror copy of Xcode that downloaded much
faster.

In the meanwhile, someone happened to replace one of China's mirror Xcode with
a fake and possibly malicious version, and many developers built their Apps
using that fake software thinking it was the same as original. [A computer
security firm FireEye claims](https://www.fireeye.com/blog/executive-
perspective/2015/09/protecting_our_custo.html) that over 4,000 apps are fake.

> Immediately after learning of XcodeGhost, FireEye Labs identified more than
4,000 infected apps on the App Store. FireEye has since updated detection
rules in its NX and Mobile Threat Prevention (MTP) products to detect the
malicious apps and their activity on a network.

FireEye NX customers are alerted if an employee uses an infected app while the
iOS device is connected to the corporate network. Its important to note that,
although the CnC servers have been taken down, the malicious apps still try to
connect to them using HTTP. This HTTP session is vulnerable to hijacking by
other attackers.

Arstechnica wrote -

[XcodeGhost apps haunting iOS App Store more numerous than first
reported](http://arstechnica.com/security/2015/09/xcodeghost-apps-haunting-
ios-app-store-more-numerous-than-first-reported/)

> Security researchers have both good and bad news about the recently reported
outbreak of XcodeGhost apps infecting Apple's App Store. The bad: the
infection was bigger than previously reported and dates back to April. The
good: affected apps are more akin to adware than security-invading malware.

Outbreak may have caused hundreds of millions of people to download malicious
apps.

"XCodeGhost seems to be far more widespread than initially assumed,"
researchers from security firm Appthority wrote in a blog post published
Monday. "We were able to identify 476 affected apps for our customers from
within our databasewhich is far more than the initial finding of around 40
apps would suggest."

If the same kind of corruption of programs analyzing medical data happens
through Docker, that will be a big nightmare. Please check - [Is Docker for
Suckers?](http://www.homolog.us/blogs/blog/2015/09/22/is-docker-for-suckers/)
to learn about the security problems related to Docker.

