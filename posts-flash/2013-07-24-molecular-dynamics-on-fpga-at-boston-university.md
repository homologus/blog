---
title: Molecular Dynamics on FPGA at Boston University (Martin Herbordt)
categories:
- chem
---
Thesis:
<!--more-->

[SCALABLE MOLECULAR DYNAMICS SIMULATION USING FPGAS AND MULTICORE PROCESSORS](
http://www.azkhan.info/publications/DoctoralDissertationByAshfaqKhan2012.pdf)

> While Molecular Dynamics Simulation (MD) uses a large fraction of the
world's High Performance Compute cycles, the modeling of many physical
phenomena remains far out of reach. Improving the cost-eff ectiveness of MD
has therefore received much attention, especially in using accelerators or
modifying the computation itself. While both approaches have demonstrated
great potential, scalability has emerged as a critical common challenge. The
goal of this research is to study this issue and develop MD solutions that not
only achieve substantial acceleration but also remain scalable. In the rst
part of this research, we focus on Discrete Molecular Dynamics Simulation
(DMD), which achieves high performance by simplifying the underlying
computation by converting it into a Discrete Event Simulation (DES). In
addition to the inherent serial nature of DES, causality issues make DMD a
notorious target for parallelization. We propose a parallel version of DMD
that, unlike any previous work, uses task decomposition and ecient
synchronization and achieves more than 8.5x speed-up for 3D physical systems
on a 12 core processor, with potential for further strong scaling.

The second part of this research focuses on FPGA acceleration of

timestep-driven MD. We rst enhance an existing FPGA kernel to take advantage
of the Block RAM architecture of FPGAs. This results in a 50% improvement in
speed-up, without sacri cing simulation quality. We then parallelize the
design targeting multiple on-board FPGA cores. We combine this with software
pipelining and careful load distribution at the application level to achieve a
3.37x speedup over its CPU counterpart.

In the third part we create a framework that integrates the FPGA accelerator
into a prominent MD package called NAMD. This framework allows users to switch
between the actual accelerator and a simulated version, and provides a means
to study di erent characteristics, such as the communication pattern, of such
an accelerated system. Using this framework, we identify the drawbacks of the
current FPGA kernel and provide guidelines for future designs. In addition,
the integrated design achieves 2.22x speed-up over a quad-core CPU, making it
the rst ever FPGA-accelerated full-parallel MD package to achieve a positive
end-to-end speed-up.

Slides:

[Towards Production FPGA?Accelerated MolecularDynamics: Progress and Challenge
s](http://www.ncsa.illinois.edu/Conferences/HPRCTA10/presentations/chiu.pdf)

