---
title: Few Quick Comments Regarding the Website
tags: []
categories:
- blog
---
We turned off all plugins on our blog, and are planning to reinstall them one
by one after doing thorough security review. One of the most used plugins had
been the auto-translation one, which many readers from non-English-speaking
countries used to read our discussions. That will be the first one to come,
and then few other useful ones will be installed. Please bear with us for a
few days.
<!--more-->

At this point, we are working hard on implementing two things before turning
on the plugins.

(i) We expect to have a cron script that periodically checks all files in our
web directories and generates a report on any newly installed ones. That way,
we can quickly find out whether any malicious code got into our server.

(ii) Secondly, we are setting up a backup server with identical set of codes.
That way, if one server is brought down, we will switch DNS to the other one
and be online immediately (i.e. DNS propagation time). In the meanwhile, we
can work on fixing security cracks in the downed one.

We would also like to add that our comment section works in the following
manner. We screen comments for spam, but if one comment from your IP gets in,
you are deemed a trusted person. All subsequent comments from the same IP will
show up in real time.

