---
layout: post
title:  "Michael Desai: Genetic Diversity in the Interference Selection Limit"
date: 2014-04-28 14:00
categories: Simons2014
---

Skewed branching and multiple branching-- not typical of neutral.

Classical setting:
Key part of the usual toolbox is that we compute probability of genealogy and mutations separately.
The time to MRCA scales with population size, so average diversity scales with population size.
The frequency spectrum (frequency of mutations that are present in i individuals) proportional to 1/i.

We have to do something different when there is selection.
We will have to keep track of fitness along with ancestry.

Our ancestors are on average were more fit on average compared to us-- just by virtue of the fact that we exist.

Let's look at pervasive deleterious mutation.

Simple model, which is still difficult to compute with:

* N: pupulation size
* U: mutation rate
* p(s): fitness effect
* R: recombination rate

Even simpler model:

* N: population size
* U_n: neutral mutation rate
* U_d: deleterious mutation rate
* S: fitness effect

No recombination.
This is what we will analyze.

We can analyze this with the structured coalescent, stratified by how many deleterious mutations we have.
Assume a large population.

Background selection.
Strong selection process-- in the limit Ns -> infity.
Most everyone descended from people with no deleterious mutations, and after that there is a neutral coalescent within that with neutral population size $N_e = N e^{-U_d/s}$.

Weak pervasive selection, no such tidy results.
Would still like to know what these
Simulation -> two regimes.
Interfence selection when above the $N_e S = 1$ line, and background selection below.

The interference selection regime seems to be determined by the scaled standard deviation.
Interference selection is $Ns -> 0$ whle holding $N \sigma$ constant.
Lots of loci, each of which has an infinitesimal effect of fitness.

Coarse grain the fitness distribution.
This increases the selection coefficient and decreases $U_d$.
The key point is that we have to scale things to preserve standard deviation of fitness.
This is a fundamental problem of identifiability-- many different parameter values lead to identical patterns of diversity.
This takes us towards the boundary between interference selection and .

Recombination-- approximate with a lineage-block approximation.

Look at distance between sites.
Close are asexual, distant are independent.
Define linkage block is the size in which we will have on average one recombination in the history up to the MRCA.

