---
title: Introduction to Chaos and Nonlinear Dynamics for Biologists, Perl Code Included
tags: []
categories:
- blog
---
Mathematics of chaos and nonlinear dynamics are so important for biological
modeling that we thought it would help our readers, if we explain them in
simple language. The toy model presented below was already mentioned [in an
earlier commentary](http://www.homolog.us/blogs/2013/05/14/how-about-a
-chaotic-genome-assembler/), but here we will add code and other details so
that you can play with it.
<!--more-->

The concept of toy model is very important in data analysis and in
understanding 'big data' or large amount of likely useless data. For example,
imagine you are studying how people get fat. You may collect extensive amount
of data on their food habits, what languages they speak, how many sentences
they utter in a day, how many hours they sleep, but ultimately may find that
their weight gain is directly proportional to number of bottles of sugary
syrup they drink. So, the toy model is a straight line correlating weight gain
and amount of sugar input, while other factors contribute to noise.

Mathematicians studied many types of simple toy models and observed that
complex behavior appeared in very simple models as long as they included some
nonlinearity. Try this equation -

![](http://upload.wikimedia.org/math/f/d/3/fd39f52fbf1b8938f2bf300a9ebd6a15.pn
g)

It is a discrete equation and here is how to run it. Let us say r=1. We will
start with x_0 between 0 and 1 (let's say 0.5), and compute x_1=r *x_0 *
(1-x_0)=0.25. Then we will plug-in x_1 into the equation and compute x_2. Here
is the code you can play with, where r is the input parameter.

`

#!/usr/bin/perl

$r=$ARGV[0];

$x=0.5;

for($i=0; $i<20000; $i++)

{

$x= $r*$x*(1-$x);

print "$i $x\n";

}

`

[What will you see at different values of
r](http://en.wikipedia.org/wiki/Logistic_map)?

>

With r between 0 and 1, the population will eventually die, independent of the
initial population.

With r between 1 and 2, the population will quickly approach a steady state
value, independent of the initial population.

With r between 2 and 3, the population will also eventually approach the same
value, but first will fluctuate around that value for some time. The rate of
convergence is linear, except for r=3, when it is dramatically slow, less than
linear.

With r between 3 and (approximately 3.44949), from almost all initial
conditions the population will approach permanent oscillations between two
values. These two values are dependent on r.

With r between 3.44949 and 3.54409 (approximately), from almost all initial
conditions the population will approach permanent oscillations among four
values.

With r increasing beyond 3.54409, from almost all initial conditions the
population will approach oscillations among 8 values, then 16, 32, etc.

At r approximately 3.56995 is the onset of chaos, at the end of the period-
doubling cascade. From almost all initial conditions we can no longer see any
oscillations of finite period.

Beyond r = 4, the values eventually leave the interval [0,1] and diverge for
almost all initial values.

Play with the equation yourself and see how it behaves. You can think about
x_0 as the part of land on earth covered by trees, and x_1 as the the part
covered by trees next year. Imagine you have a model, where 'climate change'
increases amount of rainfall, which changes the part of land on earth covered
by trees in a nonlinear way. Or x_0 can also be proportion of bugs in a
forest, part of test-tube filled with a bacteria, normalized count of a type
of transcription factor in a cell and so on.

