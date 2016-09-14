---
title: Let's Lend Ruibang a Helping Hand to Fix SOAPdenovo2
tags: []
categories:
- blog
---
Several researchers are encountering difficulties with SOAPdenovo2 and said
that the old SOAPdenovo used to run lot faster.
<!--more-->

![Capture](http://www.homolog.us/blogs/wp-
content/uploads/2013/06/Capture10-275x300.png)

Maybe we got lucky, but we never encountered the same problem. We are not sure
whether Nick Loman's problems were only with the latest update of SOAPdenovo2
made few weeks back, or whether they appeared also in the version released
about a year ago (r223).

![Capture2](http://www.homolog.us/blogs/wp-
content/uploads/2013/06/Capture24-300x174.png)

In our case, the program always ran to completion at blazing speed (check few
test cases [here](http://www.homolog.us/blogs/blog/category/soapdenovo/)) and
gave us reasonably correct assemblies. In fact, the recently released
[SOAPdenovo-trans](http://arxiv.org/abs/1305.6760), which is a transcriptome
assembler written following parts of SOAPdenovo2, helped us assemble a large
library that we could not do with Trinity.

If you encounter problems with SOAPdenovo2, please use '1>/dev/stderr 2>log'
to run the program and send the log file to Ruibang (email: rbluo at hku dot
hk). Alternatively, you can post it here so that others can compare with their
error notes to see, whether a common pattern arises. In case you want to
venture into the source code to track the error by yourself, we discussed the
code of SOAPdenovo2
[here](http://www.homolog.us/blogs/blog/category/soapdenovo/) and in the
[wiki](http://homolog.us/wiki1/index.php?title=SOAPdenovo2). SOAPdenovo
mailing list is also very active and responses come within a day or two.

\-----------------------

Looks like Nick will be sending his read files to Ruibang. We will check with
Ruibang about any update made in the code.

![Capture3](http://www.homolog.us/blogs/wp-
content/uploads/2013/06/Capture31-300x231.png)

\-----------------------

Update: Problem solved. Please see comment section.

