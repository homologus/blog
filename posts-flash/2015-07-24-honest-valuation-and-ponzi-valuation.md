---
title: Honest Valuation and Ponzi Valuation
tags: []
categories:
- blog
---
In the thread on valuation of Oxford Nanopore, reader George spiggot commented
-
<!--more-->

> Samanta, thats now how valuations work. If they sold 5000 sequencers, and
people used 2 flow cells a month, thats 5-10 Million a month, or 60-70M per
year. Then you have price earnings ratio, have a look at Illuminas. Their
value is many times earnings. In fact today, based on a 1% earnings miss they
lost 3x ONTs value. ILMN make about $1B per year, but are worth 33Bn. Why is
that. Investors are not paid back from revenue, its not a pay day loan. As for
pacbio, their value is low, and stays low, because it hard to see how their
revenue can scale. With ONT you can see how it scales, and moves into new
markets.

George, thank you for the comment, because it is perfect time to discuss
valuation these days. As you noticed, Illumina's market valuation got whacked
by over $2B for no apparent good reason. Why?

![sc](http://www.homolog.us/blogs/wp-content/uploads/2015/07/sc-300x227.png)

Please do not consider the following discussion as financial advice, but here
is how valuation works.

\-----------------------------------------------------------

**Honest valuation**

There is one and only one way to properly value a business.

1\. You first figure out what you can earn risk-free for your money. That
answer is 3% at present.

![sc2](http://www.homolog.us/blogs/wp-content/uploads/2015/07/sc2-300x227.png)

2\. Then you determine what the business returns as dividend. Is it
sufficiently more than 3% after considering various risks? There are all kinds
of risks in running a business, ranging from simple hacker attack ([e.g.
Ashley Madison](http://fortune.com/2015/07/22/ashley-madison-ottawa-
infidelity-hack-affair/)) to explosions in chemistry lab, Chinese stock market
crash and [FDA not liking your business
plan](http://www.nejm.org/doi/full/10.1056/NEJMp1316367). A person investing
in a business needs to account for all those risks and factor in sufficient
premium over 3%. Investing in a more risky business requires higher premium.

**Question: Tech companies do not pay dividend and reinvest profits in growth. Are they valued at zero?**

If you do not get any dividend, you may substitute the profit margin of a
rapidly growing company as dividend **provided** you have sufficient
expectation of getting the money returned to you as dividend in future. Also
remember that this act of substitution adds another risk factor, because a
bird in hand is worth two in bush. For all you know, the CEO may ultimately
hike his salary and leave with the profit.

\-----------------------------------------------------------

**Ponzi valuation**

At opposite pole from honest valuation sits 'Ponzi valuation' or 'get rich
quick' valuation. It is based on how fast one can get rich by passing the hot
potato to the next wannabe genius. No other explanation needed.

Ponzi valuation relies on myth-building. You see an abundance of visionaries
trying to predict the rosy future and justify the high stock prices at the
peak of a boom. They mock anyone not agreeing with them as 'inexperienced'.

> When a person with money meets a person with experience, the person with the
experience winds up with the money and the person with the money winds up with
the experience.

Ponzi valuations rule under two conditions - (i) high debt, (ii) large amount
of opium in the market. People playing with other people's money (OPM), such
as managers of mutual/pension funds, compare companies against companies
rather than looking at absolute return. That is because no pension/mutual fund
manager lost job by following what the others are doing, but many were fired
for trying to be safe. It is even better for their careers, when they can
borrow to increase leverage and short-term performance.

Please note that our use of 'Ponzi' comes from Hyman Minsky (check [Minsky's
financial instability hypothesis](https://en.wikipedia.org/wiki/Hyman_Minsky#M
insky.27s_financial_instability_hypothesis)).

\-----------------------------------------------------------

**Which valuation is right?**

Rather than right or wrong, the more pertinent question would be 'which
valuation is risky'? Risky behavior may sometimes appear exciting, and people
get carried away without properly accounting for the underlying risks.

![online-dating-site-ashley-madison-hacked](http://www.homolog.us/blogs/wp-
content/uploads/2015/07/online-dating-site-ashley-madison-hacked-300x150.jpg)

In the context of ONT, your comment makes two assumptions justifying the $1.5B
valuation - (i) ILMN's valuation, (ii) ONT is as good as ILMN. How valid are
those assumptions?

i) **Current valuation of ILMN** \- The market valuation of ILMN, based on
which you justified the other numbers, appears to be mostly Ponzi valuation.
There had been huge pent up demand for sequencing in 2009-2012 giving an
impression of exponential growth. As of 2015, sequencing is not the biggest
bottleneck, but bioinformatics is. Even within bioinformatics, the first level
of hurdle (storage and preliminary analysis of large amount of data) is not
the largest constraint. Now the question is how to make biologically/medically
relevant discoveries from that data, given that many of the low-hanging fruits
are gone. That difficult task requires more than sequencing.

ii) **'Too much sequencing' factor** \- Let's assume that ONT becomes as
successful as ILMN. In that case, the saturating demand for more sequencing
will be satisfied by ILMN, Pacbio, ONT and BGI with their new instrument, just
to mention a few. They will eat each others margin and reduce the current
'70%' profit margin of ILMN.

iii) **How good is ONT?** \- Speaking of ONT itself, I have been watching them
for years and they always under-delivered, whereas the scientists surrounding
them (e.g. Mick Watson, Birney) hyped up the prospects without giving a true
picture of reality. Jared Simpson is the only brain around there and his work
on E. coli assembly from HMM of electrical signals is commendable. However, I
do not see Mick Watson's 'prediction' of human genome assembly from ONT this
year from that success in E. coli.

Hyping up by distorting numbers creates obstacles for anyone trying to design
efficient programs. Take the example of characterization of errors. Those
numbers are very important for designing any bioinformatics program, and in
case of Pacbio, [Mark Chaisson and Glenn Tesler wrote a fantastic first
paper](http://www.biomedcentral.com/1471-2105/13/238) providing an accurate
description of error profile. When it comes to ONT data, I am completely lost.
Are the errors random or do they have positional bias? Do the errors have
AT/GC bias, homopolymer bias? What is the relative distribution of
substitutions and indels?

iv) **Factors not under control for ONT** \- Irrespective of ONT's
performance, what will happen, if ILMN market cap falls to 2-3x revenue due to
stock market correction? Will ONT be able to raise more funds? If ONT cannot
raise money, it will have to survive on its revenue/profit and burning of
existing cash. That appears to be another big and unaccounted risk factor
going forward that is not currently taken into consideration.

\-----------------------------------------------------------

**How about stock market valuation?**

Stock market valuation goes from 'honest valuation' at the bottom of a bust to
'Ponzi valuation' at the peak of a boom. That is essentially what Minsky
described in his instability hypothesis. Moreover, you can also play this rule
in reverse and count the number of visionaries predicting rosy future to
figure out where in the business cycle we currently are.

[Here](http://www.wsj.com/articles/SB10001424127887323926104578278350413288348
) is a good example full cycle of Ponzi-->honest valuation.

> Sycamore Networks: From $45 Billion to Zilch

By SCOTT THURM and BEN FOX RUBIN

Updated Feb. 1, 2013 5:38 p.m. ET

There was a time when Sycamore Networks Inc. was the next big thinga leader in
the race to direct digital traffic across the Internet.

This is not that time. On Friday, Sycamore all but went out of business. The
Chelmsford, Mass., company said it had completed the sale of its remaining
product line and that its shareholders had voted to dissolve the company.
Sycamore ended the day with a market value of about $66 million, a humbling
end for a company that in March 2000 was worth nearly $45 billion.

