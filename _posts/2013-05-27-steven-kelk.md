---
layout: post
title:  "Steven Kelk: Recent advances in rooted phylogenetic networks"
date:   2013-05-27 17:00:00
categories: MCEB2013
---

### Steven Kelk (Maastricht University, NL): Recent advances in rooted phylogenetic networks: the long road to explicit hypothesis generation

1. Introduction to rooted/evolutionary phylogenetic networks

"Network" is a bit more general than one would like-- but there are things that are not called networks that are.
Two types:
    * "data display" or unrooted networks.
    * evolutionary or rooted networks
Will be talking about the second type.
Hypothesis of what happened-- including HGT, hybridization, and recombination.
Common abstraction-- have nodes of indegree 2 or more.
Example of PNAS paper of a bacterial gene to an invasive coffee pest.
Hybridization and recombination can be symmetric exchange of information, but HGT is directional.
Can we reconstruct a hybridization network knowing the trees that are inside of it?
Reticulation parsimony: input is a set of incongruent rooted gene trees, and want a phylogenetic network that has as few reticulation events as possible.
Solution is not unique.

Many factors can cause incongruence.
DLT reconciliations are networks-- why don't we call them such?
Some folks are running tree analyses then trying to put things by hand.
Paper by Paul Jenkins, Yun Song, and Rachel Brem using reticulation parsimony, but not many others.
Combinatorial methods that attempt to measure distance between trees (rSPR).
Statistical likelihood-based methods to determine whether incongruence is actually there.
Use low-resolution parsimony to generate hypotheses, then do something statistical.


2. Case examples.

* Inferring phylogenetic networks by the MP criterion: a case study. Jin et al MBE 2007.
   Say they have an uncontroversial species tree. Add reticulation nodes to improve fit of data to a tree.
   Do these give the same results as figuring things out "by hand."
   Overall, yes.
* Integrating sequence and topology to reconstruct-- Nakleh group, RECOMB 2008.
    Reconciliation generating hypotheses, then score them using parsomony.
    Use Bergthorsson et al data, test using SH.
* SMARTIE paper from Bloomquist and Suchard.
* Highways analysis. First Bansal analysis. Dannie Durand paper where they are add incomplete lineage sorting, and only one transfer is left.

