---
layout: post
title:  "Tandy Warnow: New Methods for Inferring Species Trees in the Presence of Gene Tree Conflict Due to Incomplete Lineage Sorting"
date:
2014-04-28 10:00
categories: Simons2014
---

###  Tandy Warnow (UT Austin): New Methods for Inferring Species Trees in the Presence of Gene Tree Conflict Due to Incomplete Lineage Sorting

Even human-chimp-gorilla hard to resolve without statistical methods.
One approach either concatenation or supertree-- doesn't always work.
Incomplete lineage sorting.
She is working on "One thousand transcriptome project" and "Avian phylogenomics project"-- lots of ILS.

Under the multiple-species coalescent, the species tree is defined by a probability distribution on the gene trees.

Standard methods:
Consistent species tree methods: MP-EST, BUCKy-pop, star-BEAST.
Inconsistent: MDC and greedy consensus.
Consistency of concatenation is not known.

MP-EST paper: http://www.pnas.org/content/109/37/14942.short

Springer and Gatesy-- are not happy about treating gene trees as observed.

Bin-and-conquer:

1. Assign genes to bins, creating "supergene alignments"
2. Estimate trees on each supergene alignment using mML
3. Combined super-gene analysis

How to combine genes into bins?
First effort: random binning.
Today: statistical binning.

Input: estimated gene trees with bootstrap support, and choose a minimum support threshold `t`
Output: partitioning of the estimated gene trees into sets:
Make an incompatibility graph and find a coloring of the nodes such that two connected nodes don't have the same clustering.
This is vertex coloring problem-- hard.
They have a heuristic approach.

Simulations: binning decreases the gene tree error by 50%.
Application to Avian species tree. Seems useful.
Error in species tree branch lengths is a problem: if you overestimate branch lengths, then you overestimate ILS.

* Trade off between data quality and quantity
* Impact of data selection
* Impact of data error
* Performance guarantees on finite data
