---
title: Study Shows Men are Better than Women in Bioinformatics (p<0.05)
tags: []
categories:
- blog
---
It is clear from the title that today's commentary is on a controversial
topic. However, the controversy being highlighted here is in different part of
the title than you likely expected.
<!--more-->

![](http://www.homolog.us/blogs/wp-
content/uploads/2012/08/Capture2-300x84.png)

Study after study come out in various medical and biological journals making
sensational claims, where a magical value of p=0.05 is used to make the point.
(Check [this
report](http://www.tandfonline.com/doi/abs/10.1080/17470218.2012.711335)
titled **A peculiar prevalence of p values just below .05** to know how
prevalent the practice is.)

That method of statistical analysis is controversial, and has been strongly
criticized by statisticians worth their salt for many decades. A 1994 article
["The Earth is Round (p<0.05)" by Jacob Cohen](http://ist-
socrates.berkeley.edu/~maccoun/PP279_Cohen1.pdf) nicely explains what is wrong
with the approach.

In fact, serious statisticians were so aghast by the misuse of the practice
that, in late 90s, they made efforts to ban Null Hypothesis Significance Tests
(NHST) from all psychology journals. From ["On the Past and Future of Null
Hypothesis Significance Testing" by Robinson and
Wainer](http://www.ets.org/Media/Research/pdf/RR-01-24-Wainer.pdf) \-

> Some in the past (Schmidt, 1996) have felt that the misuse of NHST was
sufficiently widespread to justify its being banned from use within the
journals of the American Psychological Association (APA). The APA formed a
task force in 1997 to make recommendations about appropriate statistical
practice. As a small part of its deliberations, the task force briefly
considered banning NHST as well. Johnson (1999), citing Meehl (1997), surmised
that the proposal to ban NHST was ultimately rejected due to the appearance of
censorship and not because the proposal was without merit.

You can also check ['The Null Hypothesis Testing Controversy in
Psychology'](http://www.unt.edu/rss/class/mike/5030/articles/krantznhst.pdf)
for a good review.

Let us give an example to explain what the main objection is with a section of
a fictional paper.

"_We randomly selected 75 men and 75 women from wide cross-section of the
society. They attended two hours of bioinformatics training and took the
Homolog.us Standardized Bioinformatics Aptitude Training Test (HSBATT). The
responses were graded by a computer, which assigned a score between 0-100 for
each individual. Average test scores of men came out to be slightly more than
women, and the statistical significance of the results was 0.06 (Null
hypothesis - men and women can do bioinformatics equally well). Subsequently,
we checked our data for outliers, and found that three economists did very
poorly in our tests to bias the numbers. Lack of brain among Economists is
well established, and therefore those numbers were removed. The significance
of filtered results came out to be below 0.05.

Therefore, we proved that men have intrinsic abilities to perform
bioinformatic analysis better than women._"

The above fictional section shows everything that can be done improperly with
statistical analysis. It was as if we were dying to make a point, and p=0.05
was the scientifically accepted threshold for making the point. So, we
filtered data and removed numbers until we managed to cross that magical
threshold.

What is wrong with null hypothesis testing in general? As pointed out in
[Jacob Cohen's article](http://ist-
socrates.berkeley.edu/~maccoun/PP279_Cohen1.pdf) and many other places, the
null hypothesis we wanted to prove was 'given our data, what is the
probability that men and women were equally brainy', but the null hypothesis
we actually proved was 'assuming men and women were equally brainy, what is
the probability of the unusual distribution in our data'. Those two are not
equivalent statements. To make matters worse, not only the wrong statement is
assumed to be proven, but reaching an arbitrary p-value below 0.05 tends to
allow the authors make even stronger assertion than what a probabilistic
calculation would allow.

The article Jacob Cohen linked above is well written and explains the issue
with many simple examples. We would encourage curious readers to take a look.
[Here](http://www.andrews.edu/~rbailey/Chapter%20two/7217331.pdf) is another
well written article on the same topic.

Speaking of alternatives, here is one from John Tukey, an eminent statistician
and strong critic of NHST. [A Sensible Formulation of the Significance
Test](http://forrest.psych.unc.edu/jones-tukey112399.html).

\------------------

Speaking of statistics, it is ironic that a book titled [How to Lie with
Statistics](http://en.wikipedia.org/wiki/How_to_Lie_with_Statistics) and
written by a non-statistician sold more than any textbook on the subject. From
a [well-written review](http://www-
stat.wharton.upenn.edu/~steele/Publications/PDF/TN148.pdf) of the book -

> In 1954 former Better Homes and Gardens editor

and active freelance writer Darrell Huff published a

slim (142 page) volume which over time would become

the most widely read statistics book in the history

of the world. In its English language edition, more than

one-half million copies of How to Lie with Statistics

have been sold. Editions in other languages have been

available for many years, and new translations continue

to appear. In 2003 the first Chinese edition was published

by the Department of Economics of Shanghai

University.

If you do not have the book and are in a hurry to 'enhance' your paper with
statistical lies,

[these slides](http://page.mi.fu-
berlin.de/oezbek/pub/OezbekC07-How_to_lie_with_Statistics.pdf) can help.

