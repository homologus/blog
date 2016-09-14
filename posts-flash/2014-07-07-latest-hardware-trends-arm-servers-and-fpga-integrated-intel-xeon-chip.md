---
title: Latest Hardware Trends - ARM Servers and FPGA-integrated Intel Xeon Chip
tags: []
categories:
- blog
---
We would keep our readers aware of a set of developments in the computer
hardware world. Although those changes are being led by internet companies
like Google, Amazon and Facebook, we do not see why bioinformaticians cannot
take advantage of those new trend.
<!--more-->

The biggest issue on hand is power consumption of Intel architecture. When a
company needs to run thousands of servers 24x7, the power bill and the
associated cooling costs starts to bite in big way. Using ARM-based servers is
one proposed solution.

[Applied Micro, Canonical claim the first ARM 64-bit server production
software deployment](http://www.zdnet.com/applied-micro-canonical-claim-the-
first-arm-64-bit-server-production-software-deployment-7000029958/)

> For a few years now, AMD has been saying that 64-bit ARM chips yes those
processors you usually think of as powering your smartphone or tablet are
going to play not just a big role on servers, but on datacenters and the cloud
as well.

On May 30, Applied Micro Circuits Corp. (AMCC) and Canonical, Ubuntu Linux's
parent company, will seek to show that is real technology not vaporware at a
pre-Computex demo in Taiwan.

Specifically, the two companies will be trying to show off Icehouse, the
latest OpenStack cloud release using Ubuntu 14.04 Long Term Support (LTS) in a
KVM virtualized environment running on an X-Gene-based server rack.

The X-Gene is an ARMv8 64-bit Server-on-a-Chip package running at up to
2.4GHz. It combines 10/40 Gigabit mixed signal I/O with what AMCC calls an
enterprise-class memory subsystem. Compared to x86 architectures, AMCC claims
that it delivers four-times the processor density while using less than 50
percent of the power and delivering comparable-to-better overall performance.

In the demonstration, the two companies will be deploying the OpenStack/Ubuntu
stack using Canonical's own DevOps' program Juju and Metal-as-a-Service (MaaS)
to orchestrate applications, databases and services.

Besides simply setting up the cloud, the pair will be deploying such cloud-
applications as Elasticsearch, SugarCRM, Kibana, Logstash, Hadoop and
MediaWiki. The point is to show that leading scale-out cloud services are
ready to run on 64-bit ARM architecture.

"We are pleased to offer the first ARM 64-bit Server-on-a-Chip production
silicon with full certification for Ubuntu 14.04 LTS, including all the
relevant server workloads and tools to allow commercial hyperscale deployments
on X-Gene," Applied Micro's vice-president Gaurav Singh said in a statement.
"The X-Gene plus Ubuntu offering means enterprises can now capture substantial
TCO savings for their scale-out datacenters."

How good are those ARM servers? The following two links give all pros and
cons.

[ARM says it can beat Haswell at the performance per watt game](http://vr-
zone.com/articles/arm-says-it-can-beat-haswell-at-the-performance-per-watt-
game/40287.html)

> Intels keynote at Computex was defined by its push into the mobile sector.
Indeed, Intels Tom Kilroy said the next-generation of the companys hardware
would be able to break the x86 power myth meaning that these chips would have
a total power draw similar to ARMs chips which are known for their austere
power requirements.

Intel has busted the x86 power myth, Kilroy said at Intels keynote. During the
keynote he showed off a prototype fanless Haswell-powered tablet, as a way of
demonstrating the companys resolve.

The reason why an ARM-competitive processor is an achievement for Intel is it
would allow the x86 ecosystem to expand to the mobile sector, a sector
dominated by ARM. Software written for the instruction set could run natively
on an x86-powered mobile device, giving it the advantage of a massive app-
library. Windows 8, for example, would run natively eliminating the need for
Windows RT.

So what does ARM think about all of this?

When asked, a spokesperson for the company said that ARM still has an
advantage over Intels mobile chips in die size.

Its really a question of the ARM architecture versus x86 architecture. ARMs
RISC roots allow for very scalable processors. The Cortex-A7 for example
occupies less than 0.5 mm^2 of die in 28nm [fabrication] thats less than a
tenth the size of an Intel Atom (Medfield) processor core in a similar process
technology node, ARMs Elsa Wen told VR-Zone.

[Is it possible for an x86 processor to match an ARM processor in terms of
performance per watt?](http://superuser.com/questions/640243/is-it-possible-
for-an-x86-processor-to-match-an-arm-processor-in-terms-of-perfor)

> Arm processors have been getting increasingly complex - so its an apple to
orange comparison - arm has only had a 64 bit varient for about 2 years, and
even within the same generation power use varies. Its probably fairer to
consider contemporary ARM processors and their atom counterparts as anandtech
have done here.

Most of the power use isn't the processor either - the anandtech article I
linked tends to suggest that maybe 1/4 of overall power use is the processor,
and that a clovertrail atom uses slightly over half of the ARM processor in a
surface. It also shows an interesting alternate viewpoint - to optimise
systems per component for power use (as an aside - its entirely possible that
you can get pretty significant power savings doing this off a standard desktop
platform as well). Something as simple as avoiding inefficient power
conversions can do a fair bit. On most phones, for example, your display is
probably taking up close to half your total power use.

.....

The idea that arm processors are more efficient is a bit of a myth - they've
made a different set of tradeoffs (power efficiency over raw speed) and are
moving in a different direction and a different set of tradeoffs in an attempt
to go after the server market. Intel on the other hand, is effectively
segmenting modern atom designs into server parts, desktop parts (like new
pentium models) and phones, to go after the low end. Neither design is
inherently better at everything than the other.

To fend off the ARM challenge, Intel is possibly looking into FPGA. FPGAs are
very power-efficient and reprogrammable, but has one drawback. Programming
FPGAs will require knowledge of hardware language and an entirely new way of
thinking about programming.

[Intel unveils new Xeon chip with integrated FPGA, touts 20x performance
boost](http://www.extremetech.com/extreme/184828-intel-unveils-new-xeon-chip-
with-integrated-fpga-touts-20x-performance-boost)

> The main advantage of an FPGA, other than its customizability, is that it
has monstrously high performance. In much the same way that an ASIC is by far
the fastest and most efficient way of processing a specific workload (and thus
why theyre used for Bitcoin farming), an FPGA is also very fast and efficient.
Theyre not quite as fast or efficient as ASICs, but what you lose in speed you
gain in reprogrammability (again, ASICs are set in stone at manufacturing
time).

