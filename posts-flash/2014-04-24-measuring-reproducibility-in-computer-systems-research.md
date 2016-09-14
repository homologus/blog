---
title: Measuring Reproducibility in Computer Systems Research
tags: []
categories:
- blog
---
A research group in Arizona decided to reproduce as many published claims in
computer science as possible. They built a website to track each program until
they could fully build it and test it, and you can see the results [at this
link](http://reproducibility.cs.arizona.edu/).
<!--more-->

![Total](http://www.homolog.us/blogs/wp-content/uploads/2014/04/Total-
300x225.png)

> Reproducibility is a cornerstone of the scientific process: only if my
colleagues can reproduce my work should they trust its veracity. Excepting
special cases, in applied Computer Science reproducing published work should
be as simple as going to the authors' website, downloading their code and
data, typing "make" and seeing if the results correspond to the published
ones.

To investigate the extent to which Computer Science researchers are willing to
share their code and data, and the extend to which this code will actually
build with reasonable effort, we performed a study of 613 papers in eight ACM
conferences (ASPLOS'12, CCS'12, OOPSLA'12, OSDI'12, PLDI'12, SIGMOD'12,
SOSP'11, VLDB'12) and five journals (TACO'9, TISSEC'15, TOCS'30, TODS'37,
TOPLAS'34).

The authors also wrote [a comprehensive
report](http://reproducibility.cs.arizona.edu/tr.pdf) on their findings. The
entire report is worth reading, but we found 'Anecdote 2' at the end of the
paper particularly interesting. It shows how far they are willing to go to
recover materials related to the published claims. We are giving you steps 1
(first email request), 4 (Formal Request for Email Trail) and 5 (Request for
the NSF grant application). The paper has lot more details on very interesting
responses from the professors and student (tracked through LinkedIn !) .

Step 1.

>

**A.2.1 First emails**

On October 14, 2012 we had sent this email to the authors:

>

Hi!

I'm Christian Collberg from the University of Arizona. I was

wondering if you have a copy of {SYSTEM-R} that we could

try out? We have a new {SYSTEM} and I'd like to see how

well your system handles our {TECHNIQUES}.

Thank you!

Christian

Three of the four email addresses extracted from the author list in the paper
failed, the fourth, to {PROFESSOR}, appeared to work. We received no response.

In February 19, 2013, we tried again:

> Hi again!

I'm Christian Collberg from the University of Arizona. I wrote

to you earlier to see if I could have a copy of hSYSTEM-Ri so

that we could try it out, but never received a reply. We have a

new {SYSTEM} and I'd like to see how well your system handles

our {TECHNIQUES}

Step 4.

>

**A.2.4 Formal Request for Email Trail**

We next sent a request for the emails between the authors, in order to trace
the whereabouts of the source code of {SYSTEM-R}:

> Pursuant to {OPEN RECORDS STATUTE}, the Open Records Act,

I request copies of all electronic mail between

{MAIN STUDENT}

{SECOND STUDENT}

{JUNIOR-PROFESSOR}

{PROFESSOR}

regarding the article

{PAPER}

published in

{CONFERENCE}

and the development of the

{SYSTEM-R}

system described therein.

In accordance with {OPEN RECORDS STATUTE} I request that the

electronic databases to which the following email addresses

are attached be searched:

{UNIVERSITY EMAILA ADDRESSES}.

I also request that any private (non-university) email accounts containing
work-related emails be searched.

I am willing to pay applicable fees. These records are sought in furtherance
of scholarly research, and I am employed by an Educational,

Non-commercial Scientific Institution. Therefore, I ask that fees,

other than duplication fees, be waived.

CC:

{DEPARTMENT CHAIR}

and finally stage 5 !!

>

**A.2.5 Request for the NSF grant application**

We made a formal request to the NSF for the two applications of the grants
that supported the research. In one, the Principal Investigator ({PROFESSOR}
in the discussion above) writes:

> We wil also make our data and software available to the research community
when appropriate.

Needless to say, we never received any communication from {PROFESSOR}, in
particular no explanation as to why releasing the code might not have been
\appropriate."

