---
layout: post
title:  "Evolution 2013: Mostly phylogenetic methods"
date:   2013-06-25 13:30:00
categories: Evolution2013
---


## Barber, Matthew; Elde, Nels: Genetic conflicts in the battle for iron

Has been lots of work on immunity genes, but what about more core
Transferrin like dumbell-- picks up two irons.
Most cells get their iron from transferrin.

They see rapid evolution... why?
Iron metabolism plays a major role in microbial infection.

Iron required to grow.
Ferrous state-- toxic.
Ferric state-- insoluble.
"Nutritional immunity": fight over iron.

70% of iron in human body is in hemoglobin.
Also transferrin, lactoferrin, hemopexin, haptoglobin-hemoglobin.
Bacteria can extract iron from these proteins.

PAML sees some positive selection on some lineages.
Also allows them to pinpoint locations of evolution-- mostly on the C-lobe.
Why? Lots of spots for evolution to happen!

Trypanosomes encode their own transferrin, which interacts with primate transferrins.
Also in neisseria, hamophilus.

Crystal structure.
Binding sites correspond to the dN/dS work!
Neisseria is especially adapted to human transferrin-- not even adapted to other primates.


## Schliep, Klaus; Posada, David: Maximum likelihood species tree estimation under the multispecies coalescent

Why?
Only STEM does ML.

Model is ML analog of that used in *BEAST, etc.

1. UPGMA tree for each gene
2. Optimize gene trees using ML
3. Create a species tree using GLASS
4. Optimize species tree and population of gene trees.
5. Finishing-- bootstrapping, etc.

Problems:

* ML optimization of edge length is slow in comparison to unrooted trees.
* Shared haplotypes


## Zwickl, Derrick; Sanderson, Michael: Distinguishing methodological and biological causes of gene tree discordance in phylogenomic datasets

Rice phylogeny.
Tough problem.
Taking majority rule consensus-- lots of different trees there.
Look at rooted triplets.

Summarize distribution of support.
Collect all gene trees that support a given triplet.
Can plot the count of trees with a given bootstrap proportion.
Nice!

Comparing different pipelines: gene tree flux diagram.

Differences of relative minority frequency is evidence of bias.
Can see this in their diagram.

Conclusions:

* don't make biological conclusions from a single phylogenomics pipeline
* their method can allow easy comparison of choices
* that's useful!


## Palmer, Nathan D. ; Schwartz, Rachel S.; Cartwright, Reed A.: Sampling Tree-Space Effectively Using Distance Methods

Estimate pairwise distances: `delta_{ij}`
Estimate covariance matrix of the distances: `sigma^2_{ij,kl}`
Sample N vectors of pairwise distances from a multivariate normal.
Generate trees using neighbor-joining.
Why would we do this?
We could do this pairwise to estimate variances HMM-style to take alignment uncertainty into account.

Star tree simulation where branch length variance of A and B is higher.
We would expect uniform resolution, but instead get A and B clustering together.

Covariances: Takezaki, Rhetsky, and Nei (1995, MBE).
There is a connection with bootstrap.

Simulations on big ladderlike tree.
Replicates bootstrap distribution.

Take-home-- can sample tree-space using distance methods.


## Moore, Brian; Fredrik, Ronquist; McGuire, Jim; Huelsenbeck, John: Bayesian inference of phylogeny from partitioned data

Heterogeneity across alignment.
Mixed-model approach advocated by Ronquist and Heulsenbeck.
Compare amongst mixed models using Bayes Factors.
But this is not computationally feasible.
Even if we could do this it wouldn't be perfect as there could be a smear of methods.

This motivates DPP averaging.
Description of CRP.

A separate DPP run for each substitution model parameter.
Start with every parameter having one table.
Set up "auxiliary tables," which will permit new partitions.
"AutoParts"-- will be part of RevBayes.

Simulation results.
Works pretty well.
Mean partition scheme often quite novel.



## Sukumaran, Jeet; Wu, Steven; Rodrigo, Allen: A Generic Distance Metric for Unlabeled Phylogenetic Trees and Alignments

Motivation.

1. construct profiles
2. interpolate to make profiles of the same size

Can do this with lots of types of data.

Take entries from a distance matrix and sort them from smallest to largest.
Then take some distance between vectors.
But if we have structures of different sizes, we can interpolate.

Example of phylodynamics: comparing between regimes.
Given a phylogeny, would we be able to tell what regime it came from?

MASTER program (Vaughan and Drummond, 2013) used to simulate.

Did some ABC to select the epi model for each one of the simulated phylogenies.
Summary statistics: uweighted pairwise tip-to-tip distances, weighted pairwise tip-to-tip distances, lineages through time.

Does a good job of re-finding

Are we actually ignoring tree size?
Try pruning trees.

Other idea he didn't get a chance to talk about: considering canonical reference trees and looking at distances from that.
