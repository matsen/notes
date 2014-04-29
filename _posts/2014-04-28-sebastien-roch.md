---
layout: post
title:  "Sebastien Roch: Accounting for Gene Tree Estimation Error in Species Tree Reconstruction: Quantity Versus Quality"
date: 2014-04-28 16:00
categories: Simons2014
---

f: length of short branch

Three methods that work asymptotically for three taxon case:

- Most frequent topology: R-star
- Minimum coalescence time: GLASS
- Average coalescence time: STEAC (Closest pair is the one that minimizes average uncorrected Hamming distances across genes.

What is the convergence rate when we assume the gene trees are sampled noiselessly?
R* and STEAC: takes 1/f^2
GLASS is much better: takes 1/f genes

Now start with sequence data.
Generate gene tree using the multispecies coalescent, and sequences using JC.
Have two dimensions: gene length and gene number.

Empirical work suggests that concatenation bad.
Joint work with Mike Steel.
Claim 1: for all L, there is a species tree such that ML on the concatenated sequence converges on the wrong tree as G goes to infinity.
Proof idea: take an anomalous species tree, mutation rate low enough so that ML behaves like parsimony, then compute the expected parsimony score of different topologies under the coalescent.

We can think of STEAC as being like a supergene analysis.

STEAC' means concatenate closest pair.

Claim 2: STEAC' is consistent.
Claim 3: bounds on this.
Claim 4: GLASS is very sensitive to noise-- need long branch lengths.

Can interpolate between GLASS & STEAC' using quantiles.
New method is called QuEST.
Claim 5: QuEST is consistent.
Claim 6: Bound is ~ f^2/sqrt(L)

Using information theoretic bound.
Claim 7: QuEST is pretty much sharp!

Quality vs quantity: quantity trumps quality in terms of overall sequencing effort.
