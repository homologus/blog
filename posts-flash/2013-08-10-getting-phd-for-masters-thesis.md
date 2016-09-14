---
title: Getting PhD for Master's Thesis
tags: []
categories:
- blog
---
My MS thesis was on [calculating electrical current through small molecules
connected between big metallic surfaces](http://chem-
faculty.ucsd.edu/kubiak/publications/79.pdf). We used Green function method,
which is another way of calculating wave functions in quantum physics and is
more amenable to computer simulation. In section titled 'COMPUTATION OF
TRANSMISSION FUNCTION OF THE MOLECULE' of our paper, we wrote -
<!--more-->

> However, we feel that the Green-function method is more powerful and
versatile in handling the open boundary condition associated with the semi-
in?nite contacts.

True, but there is one problem. How does one simulate semi-infinite system?
You will not understand the concept of computers being less powerful than
mathematics (and even less powerful than computer+math together), unless you
try to solve such numerical problems yourself. No matter how many processors
you have, finite cannot simulate infinite.

I solved it in a clever way by adding a small negative imaginary number to the
matrices composed of real numbers. There was no physics-based reason for doing
that, but some kind of intuition told me that an imaginary number could work
as a damping factor in real matrices and allow the recursion to converge. It
was a hare-brained scheme concocted on a Friday night, but it worked !!

In those days, my adviser (a brilliant professor) did not use computers to do
simulation and did not realize the mathematical complications in modeling
semi-infinite system. So, the details were buried in my MS thesis.

![](http://www.kutl.kyushu-u.ac.jp/seminar/MicroWorld2_E/2Part3_E/2P31_E/SQ_we
ll_E.jpg)

Fast forward by 18 months. Armed with Matlab, he decided to run those 'easy'
simulations himself and got stuck with the same problem. No matter how big he
made his matrices, the program always returned a noisy curve with many peaks.
Here is what happened. In a finite quantum system, the waves always bounce
from one end to other and create standing waves. Those standing waves give
rise to spurious peaks in the energy distribution. I do not remember, whether
Matlab could invert 1000x1000 matrices in those days, but even 1000x1000 is
too small to avoid standing waves. You really have to model semi-infinite
systems to get nice, clean curves as in the linked paper. Moreover, after a
finite simulation, it becomes tedious to figure out which peaks are real and
which are spurious. Why did not the physicists have a solution? It was because
the condensed matter physicists had ways to deal with infinite systems, but
they rarely dealt with semi-infinite systems and even more rarely on current
transport in such system. We, electrical engineers, had to fill the void.

After my professor got stuck with his matrices, I was invoked. This time I had
to give a full presentation of the 'imaginary number trick' to simulate semi-
infinite Hamiltonian system. He was so impressed, he let me leave with a PhD
in 2 years and 4 months !

That begs the question - what happened to the PhD thesis? Yes, I did write a
PhD thesis and solved another hard mathematical problem (difficult enough for
me :)). This time I worked on the electric conduction between superconductors
forming Josephson junctions, and especially between d-wave superconductors. By
that point, I was losing faith in computer simulations and realized that
simulations only drew plots, but gave no real insight until I could also
derive the same thing in mathematical terms. Simulations 'make sense', only if
you know the answer. On the other hand, f you know the results already, why
would you study a physical system?

Going full math required me to connect the Green function equations with the
wave-functions (as done in traditional physics), but for semi-infinite
systems. That was not easy at all and especially not for superconductors with
unusual order parameters and electrons and holes. My professor worked out few
simple examples on s-wave superconductors, and those were helpful. I remember
spending the entire summer of 1997 sitting with reams of papers with
equations, but I finally managed to connect the waves with Green functions to
get a nice compact formula.

I was done in 1997 and never went back to the topic. Our paper was [published
in Physical Review](http://prb.aps.org/abstract/PRB/v57/i17/p10972_1) and sat
there for a long time without citation. The way things work in mathematical
physics is that unless another researcher gets stuck on the same problem and
spends months, there is no way others can appreciate the 'mathematical beauty'
of a solution. That was the case with my MS thesis and was the same with my
PhD thesis. In fact, I never expected anyone to come across the same problem
for decades, because in those days physicists avoided current transport and
electrical engineers were too afraid to deal with quantum physics. Add
superconducting junctions to the mix and you get a big community of 0 persons.

**I was wrong !!** Three papers came out in physics journals since 2011 and mathematical derivation in my PhD paper is starting to get citations. Two of them are shown below and I also show the exact location of citation in one of them. 

![Capture2](http://www.homolog.us/blogs/wp-
content/uploads/2013/08/Capture25-300x221.png)

![Capture](http://www.homolog.us/blogs/wp-
content/uploads/2013/08/Capture16-300x250.png)

![Capture3](http://www.homolog.us/blogs/wp-
content/uploads/2013/08/Capture32-226x300.png)

This long story has a different conclusion than what you expect from the
title. It is not about physics, equation or papers, but on what we wrote in
[Top N Reasons NOT to do a Ph.D. in Bioinformatics/Computational
Biology](http://www.homolog.us/blogs/blog/2012/08/11/top-n-reasons-not-to-
do-a-ph-d-in-bioinformaticscomputational-biology/) and elaborated in [Our
Vision for Biology of 21st Century](http://homolog.us/Social/our-vision-for-
biology-during-21st-century/).

To spare you from reading those posts, I will give you the summary here -

> Instead of being all negative, we also like to make some constructive
suggestions to young students. If there is one thing homolog.us blog would
recommend to young biology students, that is to learn Chinese and translate a
biology paper to Chinese. It is far more important language to learn at this
point of your career than C, C++ or Java.

We noticed that all recent citations of our paper came from China and Hong
Kong. In fact, the senior author of the Phys. Rev. B paper was in Penn State
before moving to Hong Kong. Essentially, USA is driving out the mathematically
skilled scientists and promoting [those like positivity
lady](http://www.homolog.us/blogs/blog/2013/08/05/tragedy-of-the-day-pnas-got-
duped-by-positivity-lady/). If that appears to be a winning strategy, I have a
bridge to sell you from my backyard.

![](http://s3.amazonaws.com/dk-
production/images/33748/large/I5_bridge_collapse_screenshot.jpg?1369396040)

(From [No deaths reported in Washington state bridge
collapse](http://www.dailykos.com/story/2013/05/24/1211403/-No-deaths-
reported-in-Seattle-bridge-collapse))

In biology, the central planners are increasingly getting desperate to see
immediate results or immediate application of funded rsearch. In contrast,
Tony Pawson said in ["Thinking about How Living Things
Work"](http://www.inamori-f.or.jp/laureates/k24_b_tony/img/lct_e.pdf) \-

> Remarkably, the basic science that has been pursued over several decades
into the nature of cell communication, and the mis-wiring of signaling
pathways in disease, is starting to yield new targeted therapies that are
changing the way that we treat cancers for the better, and will be applicable
to many human ailments. Although these are early days, I believe that this
progress underscores the importance of giving free rein to human
inventiveness. It would have been hard to predict that work on a curious
chicken virus would have ultimately led to new ways of thinking about how
human cells are organized, and to new drugs to treat one of mankinds most
persistent enemies. Governments increasingly want to see immediate returns on
the research that they support, but it is worth viewing basic science as a
long-term investment that will yield completely unexpected dividends for
humanity in the future.

Even restricting ourselves to bioinformatics, we can clearly see the bias
against mathematics and towards 'tools' with immediate application. For
example, check the difference in number of citations of the three following
papers. We agree that BWA and Bowtie have been very helpful tools, but the
ratio of citation-count grossly undermines Lippert's contribution. That forces
everyone to build software packages and leads to [an exponential increase in
the number of mapping tools](http://www.homolog.us/blogs/blog/2013/08/06
/mapping-algorithms-how-they-all-arrived/) instead of proliferation of novel
mathematical ideas to be used in shared packages.

![Capture](http://www.homolog.us/blogs/wp-
content/uploads/2013/08/Capture17-300x60.png)

![Capture2](http://www.homolog.us/blogs/wp-
content/uploads/2013/08/Capture26-300x60.png)

![Capture3](http://www.homolog.us/blogs/wp-
content/uploads/2013/08/Capture33-300x59.png)

Please feel free to voice your disagreement in the comment section.

