---
title: Kalman Filter - a Way to Reconstruct Signal from Noisy Data (as in Nanopore)
tags: []
categories:
- blog
---
By now, we know quite a bit about Oxford Nanopore's experimental system from
[their publicly filed patent
applications](http://www.homolog.us/blogs/blog/2013/10/27/everything-want-
know-oxford-nanopore/). The sequencer is composed of DNA molecule passing
through a small pore, and the patents suggest a few possibilities for that
pore-containing molecule. When the DNA passes through the pore, it produces
some kind of noisy electrical signal. The challenge is in removing the noise
and coming up with the actual signal. We have not seen any bioinformatics
patent suggesting that the company did not come up with an elegant way to
remove noise.
<!--more-->

PacBio has shown that if someone has multiple noisy copies of long DNA
sequence, it is possible to reconstruct the correct sequence at 99.99%
accuracy. Some kind of Hidden Markov Model (HMM) or Bayesian algorithm is
needed to do that. However, that at least requires a base-calling step, but is
it possible to start from the noisy electrical sequence, skip the base calling
step and go straight to error correction?

![Capture](http://www.homolog.us/blogs/wp-
content/uploads/2013/10/Capture24-300x191.png)

A large part of research on HMM were done by electrical engineers in 1950s and
1960s, when they tried to reconstruct communication signal passing through
noisy channel. [Sean Eddy made a career in bioinformatics by blissfully
appropriating that research](http://www.homolog.us/blogs/blog/2013/08/03
/hmmer-and-viterbi-algorithm/). We use the description 'appropriation',
because he not only did not cite Viterbi in his book, but rather went to the
extent of copyrighting the 'HHMer' name to stop electrical engineers from
writing a hardware-accelerated version. Petty complaints aside, what else did
the electrical engineers produce that bioinformaticians can appropriate?

As it appears, Kalman filter has not been used extensively in bioinformatics,
and definitely not in topics related to reconstructing nucleotide signals.
Kalman filter and extended Kalman filter became useful, because HMM was
relative slow. Nanopore signal can be used as a time series to use these
techniques, but we do not know what kind of difficulties will be posed by the
variable speed of data arrival (i.e. DNA molecule passing through the pore at
different speed).

[Kalman filter](http://en.wikipedia.org/wiki/Kalman_filter)

> The Kalman filter, also known as linear quadratic estimation (LQE), is an
algorithm that uses a series of measurements observed over time, containing
noise (random variations) and other inaccuracies, and produces estimates of
unknown variables that tend to be more precise than those based on a single
measurement alone. More formally, the Kalman filter operates recursively on
streams of noisy input data to produce a statistically optimal estimate of the
underlying system state. The filter is named for Rudolf (Rudy) E. Klmn, one of
the primary developers of its theory.

The Kalman filter has numerous applications in technology. A common
application is for guidance, navigation and control of vehicles, particularly
aircraft and spacecraft. Furthermore, the Kalman filter is a widely applied
concept in time series analysis used in fields such as signal processing and
econometrics.

The algorithm works in a two-step process. In the prediction step, the Kalman
filter produces estimates of the current state variables, along with their
uncertainties. Once the outcome of the next measurement (necessarily corrupted
with some amount of error, including random noise) is observed, these
estimates are updated using a weighted average, with more weight being given
to estimates with higher certainty. Because of the algorithm's recursive
nature, it can run in real time using only the present input measurements and
the previously calculated state; no additional past information is required.

From a theoretical standpoint, the main assumption of the Kalman filter is
that the underlying system is a linear dynamical system and that all error
terms and measurements have a Gaussian distribution (often a multivariate
Gaussian distribution).

Extensions and generalizations to the method have also been developed, such as
the extended Kalman filter and the unscented Kalman filter which work on
nonlinear systems. The underlying model is a Bayesian model similar to a
hidden Markov model but where the state space of the latent variables is
continuous and where all latent and observed variables have Gaussian
distributions.

