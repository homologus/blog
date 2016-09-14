---
title: What is in the News?
tags: []
categories:
- blog
---
Although it may seem odd at first, the following discussion is related to
comparison of sequences from Pacific bio, Illumina, SOLiD, etc.
<!--more-->

If, in year 1912, one thousand school-kids were asked to predict the headline
news 100 years later, could any of them have guessed that it would be related
to cannibal roaming in Florida?

![](http://www.homolog.us/blogs/wp-
content/uploads/2012/06/Capture1-300x180.png)

To understand the context, place yourself in the year 1912. Although a large
part of US population was living on low-tech farming at that time, the
potentials of industrialization were already understood. Over the previous
century, society benefited from tremendous technological progress. Railroads
connected large part of the continent and cars were getting introduced.
Introduction of electricity and light bulbs ended candles and dark nights.
Other technologies widely accepted as normal (and backdated) today were being
implemented at that time, land-line telephone being the prime example. What
would be the world like 100 years later?

This is not a moral or philosophical commentary, but rather a discussion on
mathematics of news. Do you see a fallacy in the above discussion? It is in
the difference between two questions - (i) 'what would the world be like 100
years later' and (ii) 'what will be top news'.

What is news? Is sun rising on the east newsworthy? No, because everyone
expects it. Will it be news, if sun rises on the west tomorrow? You bet !! If
you sequence a new genome and find Cs matching Ts and As matching Gs on
opposite strand, that will definitely create a big buzz, because the
probability of such observation, based on our current understanding, is
extremely low.

Mathematically, we can say that newsworthiness of an event is inversely
proportional to the probability of its occurrence. So, when one thousand
school-kids were asked to predict the headline news, they were expected to
figure out what would be very unusual 100 years later. Flesh-eating zombie
roaming in Miami definitely cuts to the top of the list.

In 1948, Claude Shannon wrote his seminal paper on [A Mathematical Theory of
Communication](http://cm.bell-labs.com/cm/ms/what/shannonday/shannon1948.pdf),
where he used the above concept to define '[information content](http://en.wik
ipedia.org/wiki/Information_theory#Quantities_of_information)' of the messages
being sent and received. Shannon's objective was to compare qualities of
various communication channels, which is conceptually similar to comparing
various sequencing technologies.

Typically, when we ask people around about various sequencing methods, the
answers we get are very subjective.

'ABI SOLiD generates an order of magnitude more data than Illumina, but they
are more noisy.'

'Pacific bio sequences are very long, and that is what we need.'

'I like Illumina, because their sequences are very clean.'

'Even though PacBio sequences are long, they are too noisy and cannot be
used.'

Conceptually you can think of the real sequences as the messages before
transmission and sequences derived from various technologies as messages after
transmission through a communication channel. Then we can fit Shannon's
mathematical approach to find a more objective comparison between various
technologies. Is it worth paying more for longer PacBio sequences? The
question can be answered objectively by using methods already derived for
comparing communication channels.

