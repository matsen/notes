---
layout: post
title:  Short talks Day 3
date:   2013-05-30 11:00:00
categories: MCEB2013
---

Each cytotoxic T lymphocyte (CTL) targets a single epitope.

How much killing are the CTLs doing?
Asquith et al PLOS Biol, Fernandez et al 2005 in JV.
Fit a model to 1990's data. Sometimes work, sometimes not.

In first month of infection, CTL's target about 3 epitopes.
HIV escapes these epotopes through 1-10 possible mutations.
Typically a single starts the infection.

Can we use the simple method for this new type of data?
Introducing "escape graph" concerning mutation of epitopes.

Model of evolution (Perelson, Nowak); formalize with a branching process.
Infer the kill rates k_v.
Hypothesis test framework: calculate p-values using simulation


## Sophie Lèbre (Strasbourg): An evolution model for Limited Insertion Independent from Substitution

Review:
* TKF91 model: Birth rate lambda and death rate mu of gaps
* McGuire 2001 introduce F84 with a 5th residue representing a "gap"
* Rivas (2005), Rivas and Eddy (2008) introduce a non-reversible model
explicit parameters for insertion and deletion.

Goal of her talk: insertion and deletion independent of the substitution model, for say, GC content evolution.
IDIS model: Insertion Deletion Independent of substitution

BD process with birth `r_i n(t)` and death `d n_i`.
Can write down differential equation for the mutational process and use variation of parameters to solve evolution for the entire process.

Example merging with HKY model.

Example for GC content. Can derive CG content over time.

Now add "limited" part by adding a term that brings the length down.

## Matthew Hartfield (Montpellier): Determining effect of HCV genotype of outcome

Importance of heritability?
People usually point to host genetics.
Alizon et al (2010) used a phylogenetic method to show lots of influence of HIV genotype.
HCV shows two main infection outcomes: natural clearance or chronic.
There are several SNPs on the host side that make a difference.

Use ML method to estimate rate of trait-changing.
This will determine our estimate of importance of that trait.

HCV data from Australian prisons (HITS)!
Fall into two clusters.
Not significant difference between rate of clearance looking at phylogenetic tree, i.e. virus genotype.

Now looking at SNPs and their impact: repeat same analysis for the SNP.
That does appear to be significant(?)

OK, so now use BayesTraits to re-estimate rates of clearance controlling for host genotype.
See a significant impact.

## Peter F Arndt (Max Planck Institue for Molecular Genetics): The evolutionary fate of duplicated neutral DNA-- breaking sticks on evolutionary time scales

Title from the evolutionary fate and consequences of duplicate genes (Lynch and Conory, Science 200)
ENCODE annotations: 2013.
Example of 67 BP that is identical between two sites on chromosome 1.

Today: quantify how often it occurs.
Self-alignment -> match length distribution.
See lots more than one would expect.

Many transposable elements matching-- eg Alu and Lines.
What is left is segmental duplication.

Two components: random matching is linear, and the second one is a power law.
Exponent of power law is -3 (Gao and Miller, 2011).

Big segmental duplication is like one stick.
Then we randomly introduce mutations (mis-matches) which break the stick.
This is stick-breaking process (Kuhn 1930.
Ziff and McGrady, 1985, wrote down differential equation describing dynamics.

Say we have duplications appearing with a given rate, and being split at a certain rate.
Stationary process -> can derive the distribution of stick lengths.
See power law!

Q: Why don't we see same pattern for Alu?
A: More complex pattern of repeat introduction


## Filip Bielejec (KU Leuven): Epoch substitution models

Central assumption of time homogeneity allows us to do Felsenstein recursion.

For an epoch model we can just split an edge in two and then multiply the two matrices.
Use fine-scale parallelization to multiply matrices, and coarse-grain parallelization to calculate around the tree.

Re-analyze Shankarappa et al (1999) data set.
Slowed down rate of evolution for HIV.

* immune relaxation: less pressure on virus
* cellular exhaustion: fewer target cells.

Run two-epoch discretization with separate GY94.
See significant plots, and Bayes factors.
Also support immune relaxation is supported from omega being greater than one.

Seasonal circulation of flu.
Use Bayesian stochastic search variable selection (Lemey et al 2009) to look for differences in terms of seasonality.

* Q: Mixing problems?
* A: No. Chapman-Kolmogorov allows us to make a smooth transition.


## Samantha Lycett (Edinburgh): Bayesian methods for detecting epistatic interactions in flu

Two types of interactions: structural ones (e.g. polymerases). Functional ones (e.g. between HA and NA in that HA needs a good NA in order to be fit).

We are going to be looking for statistical signatures.
NA drugs have been in use since 1999.
Experiments have shown that oseltamivir-resistant NA are less fit, but there has been a rapid increase in drug resistance.
Possible explanations: permissive mutations in NA, or hitch-hiking.

H1N1 seasonal data, sub-sampled to 3 per country.

Have to be careful about founder effect, which will look like epistasis.
Have to take tree into account.
Want to look for independent introduction of double mutations-- "mapping method".
Second method to look for mutations that happen in quick succession-- "modeling method".

Reconstruct ancestral sequences, and apply mapping method.
See some mutations, but can't rule out multiple testing.
Not a lot of signal to use.

Next, modeling method.
Use likelihood ratio test for the coevolution
Use ACE package in R on simulated data, as well as BEAST.
Can find signal when put it in simulations.

Find NA222 and NA 344-- permissive mutations.

