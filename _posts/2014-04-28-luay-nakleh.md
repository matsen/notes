---
layout: post
title:  "Luay Nakleh: Modeling the Evolution of Genes and Genomes in the Presence of ILS and Hybridization"
date: 2014-04-28 14:00
categories: Simons2014
---

Two sources of species tree discordance: ILS & hybridization

Focus of his work: find probability of gene tree given species trees in the presence of ILS and hybridization.
They project down to coalescent histories, which are embeddings of gene trees in species tree.
Gives overview of Degnan and Salter 2005 derivation of the ILS likelihood.
Comes down to enumerating one-population coalescent events.

Can't just talk about trees contained in networks when we have ILS.
One network gets mapped to one multi-labeled-tree -- called a MUL-tree.
The probability of an hybridization network can be calculated as the sum over ILS-trees that will make hybridization.

Have to explore different levels of criteria.
Compare using information criteria and cross-validation.

Mouse data sampled across Europe.
Also the Rokas data.

Now would like to infer site-wise ancestry.
Map out using HMMs-- can do posterior decoding.
