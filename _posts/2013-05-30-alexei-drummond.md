---
layout: post
title:  "Alexei Drummond: Bayesian molecular epidemiology"
date:   2013-05-30 9:00:00
categories: MCEB2013
---

Defining phylogeny to be a time-tree: heights of internal nodes are specified.
Need not be ultrametric.
Showing BHV-like space for time-trees.
Felsenstein likelihood.
Likelihood surface exploration: we are blindfolded and can only feel with our feet.
MCMC overview and Hastings ratio.
Densitree!
They are writing a little book about BEAST 2!
Describing calibrated phylogenetic inference with timed leaves.

Phylodynamics-- intersection of phylogenetics and mathematical epidemiology.
Coalescent process.
Skyline plot.

Sometimes these nonparametric approaches miss things-- e.g. if you have a sinusoidal change in population size, only can fit up to most recent bottleneck.
However, if you have multi-locus data or data through time, you can go back through a number of different cycles.

Birth-death processes.
Stadler, 2010 birth-death-serial-sampled (BDSS) tree prior.
Per-lineage dynamics are captured by a simple set of rate equations.

R_0 = 1 + g/d

at the beginning of an epidemic, where g is growth rate and d is death rate.

Estimating growth rate using the BDSS is more accurate than the coalescent.
Can estimate things like reproductive ratio of the virus to get an idea of the progression of the epidemic.
New paper by Vaughan and Drummond describing stochastic simulator MASTER of BD epidemiological processes.
Stochastic version of replication dynamics.

Now on to sampling internal nodes, i.e. having sequences appear in the middle of edges.
A lot more trees that have sampled internal nodes than

Proposal mechanism: extend the Wilson-Balding operator.
Can move subtree onto a leaf.
Examining prior.
Can't talk about clades in quite the same way-- have to take

Sampling trees with structure, like Beerli's Migrate.
E.g. Wright-Fisher model.
To sample we have to introduce new operators that can add or remove migration events to the ancestral history.

Beerli and Felsenstein (2001) proposal involving new lineages.
Ewing, Nicholls and Rodrigo (2004) have a very simple proposal distribution that adds migrations in the middle and also lets them move up and down.
Operator design strategy: tree moves, and re-do migrations according to destination edge "color."
Use uniformization method of Fearnhead and Sherlock (2006)-- find end states first, then fill in the transitions.
Order of magnitude improvement in ESS.

Multi-type birth-death process: wanting to extend multiple sample BD process to multi-deme setting.
Involves numerical integration, and unfortunately slow.
Application to flu.
Coalescent and BD give different answers.

Perfect synthesis would be:

* fully stochastic approach
* all processes, including microscopic, modeled
* retains non-linear coupling between types and hosts
* handles both neutral and selected variation
* parameters can be readily connected with measured quantities
* simulation, analysis, and inference tools.


* Q (McVean): what are you trying to get beyond the coalescent.
* A: Our idea is to try to put everything in and see if it does make a difference.
* Q: Can you see selection going on?
* A: Example of within- and between- host evolution in HIV. The evolutionary adaptations don't help you in the next host.
* Q: Can we predict how long a given BEAST run will take?
* A: If we take dumb operators, runtime can vary by an order of magnitude, but with smarter operators we can get lots better predi



