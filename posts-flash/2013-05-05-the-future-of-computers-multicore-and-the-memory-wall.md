---
title: The Future of Computers - Multicore and the Memory Wall
tags: []
categories:
- blog
---
A number of dignitaries are coming to eat breakfast at Intel ex-CEO Craig
Barrett's house, but the resident cook is very slow. Will adding 10 more cooks
get breakfast ready in time?
<!--more-->

>

Start with a single cook in a small kitchen to scramble eggs.

Add another to fry bacon in parallel with the first doing the eggs, and making
breakfast goes a bit faster.

Add another to brown, butter, and slice the toast, and you might gain a bit
more speed.

Yet another person can set the table, pour the juice, and serve.

It is still not fast enough so you add a dozen more cooks to get that "magic",
"exponential" increase in performance.

There are problems however.

The first four cooks all need to use the refrigerator. In our culinary world
each would twiddle his thumbs waiting his turn. This is the physical world
equivalent of "contention between processors of the memory bus."

Now how much faster do you think breakfast will be ready when those additional
dozen cooks are added? As Borat would say, "Not so much."

Very similar situation appears in Intel's multi-core architecture, because
attempts to use the cores in full throttle creates large bottleneck at the
memory interface. Following two articles from 2011 explains the problem in
very lucid language.

[The future of computers - Part 1: Multicore and the Memory
Wall](http://www.edn.com/design/systems-design/4368705/The-future-of-computers
--Part-1-Multicore-and-the-Memory-Wall)

[Future of computers - Part 2: The Power Wall](http://www.edn.com/design
/systems-design/4368858/Future-of-computers--Part-2-The-Power-Wall)

