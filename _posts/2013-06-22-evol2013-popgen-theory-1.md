---
layout: post
title:  "Evolution 2013: Population genetics theory I"
date:   2013-06-22 08:30:00
categories: Evolution2013
---

## McLaren, Michael: Fitness-valley crossing in subdivided populations

Definition of sequential fixation.
Definition of stochastic tunneling.
Simulation of Weinreich and Chao (2005)
Tunneling actually gets faster when population size
There is a crossover time when sequential time is equal to tunneling time.

What happens when we have subdivided demes?
How does expected valley crossing time depend on migration rate?

Island model with migration rate m. Overdominance h.

How does genetic differentiation affect selection and drift?
F_{ST} = variance between demes / total variance = corrleation of alleles within demes

Result clear when m=0 and m=1.

Mutation-selection balance approximation based on Whitlock (2002).
Branching process approximation of Weissman et al(2009) with drift and seelction rescaled.

Can derive expression for strongly deleterious intermediates and general h.
Can increase or decrease fixation time depending on h.


## McCandlish, David; Epstein, Charles; Plotkin, Joshua B.: Adaptation: The inevitability of deleterious fixations during adaptation

Fitness trajectories: watching the expected fitness through time.
We would expect that fitness trajectories would be monotonic.
Can show existence of non-monotonic trajectories.

Moran, weak mutation, House of cards model for fitnesses.

Going to be discussing the expected substitution constant.
The expected selection coefficient of the first substitution is negative for a population whose initial fitness is greater than the critical fitness
This critical fitness is less than the asymptotic fitness.

Key is very low frequency alleles that are very fit.

A deeper theorem: can derive distribution of fitnesses of first substitution.

Even without fancy things such as fitness valleys, can show that first substitutions are going to be deleterious.


## Kosheleva, Katya; Desai, Michael: The Dynamics of Genetic Draft in Rapidly Adapting Populations

Basic model of a

Two regimes of adaptation:

1. t_fix << t_est (time to a new mutation)
2. t_fix >> t_est, this is called genetic draft

Evolving yeast for 1000 generations, see lots of stochastic events, so draft.

Fitness wave of adaptation.
We are interested in the fate of a single clone.
Surfing on the front of the fitness wave.

Simulations. We only need to consider the wavefront-- high fitness.
Can apply this to derive site frequency spectrum and sojourn times.

## Lan, Yinghong; Weinreich, Daniel M.: How High-order Epistasis Influences Robustness and Evolvability of Fitness Landscapes

Intro to fitness landscapes and epistasis.

* Robustness: difference between highest fitness genotype and the mean of its nearest neighbors.
* Evolvability: difference between lowest fitness genotype and the mean of its nearest neighbors.

Relationship between these two is complex.

Walsh transformation. Hadamard matrix!
Multiply Hadamard matrix on left by the fitness fitness values and get the epistasis terms.
This is invertible.
This shows that pairwise epistasis terms couldn't be completely determining fitness spectrum.

How do fitness and evolvability relate?
Assume that epistasis coefficients on the same order are equal.
Negative pairwise epistasis allows increased evolvability without changing robustness. Complicated with pairwise epistasis.
3 and 4 bit cases give similar results.


## Harris, Kelley; Lorenzen, Eline; Fumagalli, Matteo; Liu, Shiping; Willerslev, Eske; Nielsen, Rasmus: The effects of population size fluctuation and coalescent model choice on inference of population structure from shared haplotype tracts

Genealogies are constrained by a species tree
Classical phylogenetic inference problem: infer TMRCAs.
Can be complicated by gene flow, but infinite sites model is accurate, and can infer past effective population sizes.

Want to look at the whole genome, and estimate plot of TMRCA along the genome.
Lots of hidden markov models, Li and Durbin, Mailund, Song.
Infer demography from trats of identity by state (IBS)
Use lengths of these tracts to infer coalescent times.
Recently published in PLOS genetics.
Looks good with simulation.
Don't need to get TMCA of individual genes.
Application to divergence of brown and polar bears.
Demographic analysis with CoalHMM, assumes isolation with migration, makes 5 millions year prediction, which is surprising, previous work says 1/2 million years.
Then they fit a more complex model, including bottlenecking, and with that they were able to get a better fit.
