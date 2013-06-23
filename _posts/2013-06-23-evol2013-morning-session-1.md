---
layout: post
title:  "Evolution 2013: Morning session I"
date:   2013-06-23 08:30:00
categories: Evolution2013
---

## James, Ho, Lam; Ane, Cecile: A linear-time algorithm for Gaussian and non-Gaussian trait evolution models.

Linear model for a Gaussian trait-- expensive.
Felsenstein (1973)-- use independent contrasts.
Freckleton (2012)-- reintroduce this method.
FitzJohn (2013)-- fast method.

We develop a linar time algorithm to calculate
* det V
* P^T V^{-1} Q

Need to have that the covariance matrics are tree structured - they show this is equivalent to covariance among tips of Brownian motion on some tree.
If V is tree structured, then V is a rank-1 perturbation of A.
Get block structure. Leverage this for efficient computation.

Applications.
Can do O-U model with several selective regimes.
Phylogenetic prediction.
Phylogenetic PCA.
Phylogenetic logistic regression.
Phylogenetic GLM.

Implementation in R package phylolm.
It's quite fast.


## Smaers, Jeroen: A variable ratesapproach to quantifying the processes assessing co-evolution

If we are looking at something like brain/body ratio, if it changes we don't know which one changed.

Summarize whatever happens in the rest of the tree with a posterior on the trait value at an internal node.

Then we can decide which one matters.

* Characterize adaptive peaks
* Quantify deviation from the peaks. Use a metric space approach to quantify this.

Can use fossils to validate or calibrate the model.

Independent setup allows us to understand the numerator and the denominator.

Application: brain and body side often occur independently of each other.


## Burmeister, Alita; Meyer, Justin; Lenski, Richard: Coevolution Facilitates the Evolution of a Novel Function in Phage Lambda by Altering the Fitness Landscape.

How does novelty come about?
Fitness valley can be traversed by environmental change.
Environment may be co-evolution.
Bacteriophage.

Lambda's fitness landscape.
Can see coevolution between Lambda and host binding.
Saw shift from LamB entry to OmpF entry.
Is this a fitness valley?
Four key mutations occur in parallel.

Today: experimentally determine if these mutations are adaptive.
Does the host environment matter?
Infect ancestor host or evolved host and ancestor virus and evolved virus.
Can see them because different color.

Expect to see change of fitness between the two environments-- new virus more fit in new host.
Saw that, but also also saw that intermediates are adaptive.

What are the mechanisms of adaptation?
Resource competition.
Demonstration that fitness is a resource competition thing.



