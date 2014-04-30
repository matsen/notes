---
layout: post
title:  "Amaury Lambert: From Individual-based Population Models to Lineage-based Models of Phylogenetic Trees"
date: 2014-04-28 14:00
categories: Simons2014
---

Take time-calibrated phylogenies as data.

For example, topological balance beta, and relative branch lengths gamma.

Lineage-based model-- birth-death model.
Birth and death rates may depend on time t, number n of standing particles, a non-heritable trait a, and a heritable trait i.
Assume mother keeps the trait, and the daughter splits to the right.
Remove extinct tips.

Lambert & Stadler, 2013:
- same topology as Yule trees iff birth rate in terms of t and n only, and d depends on t, n, and a.
  -> such trees cannot explain imbalance
- likelihood of reconstructed trees always has an explicit product form iff b is a function of t and d is a function of t and a only.

Coalescent point process-- oriented tree whose node depths form a sequence of iid random variables $H_i$ killed at its first value larger than T.

If b is a function of t and d is a function of t and a only, the reconstructed tree is a CPP with typical node depth H, whose law is implicitly defined.
Also works with extinction rate.

Application to bird phylogeny-- extinction rate increase with age.

Now particles are populations.
Every population starts as an incipient population, then they become "good" at some random time to make a new species.

Reconstructed tree spanned by extant representative populations at T is a coalescent point process with a node depth with a computable density.


