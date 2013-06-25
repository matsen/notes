---
layout: post
title:  "Evolution 2013: Informatics"
date:   2013-06-24 08:30:00
categories: Evolution2013
---

## Smith, Stephen A; Brown, Joseph; Hinchliff, Cody: Analyzing and synthesizing the tree of life using graphs

All trees are rooted-- think of a tree as being a collection of directed edges.
Build graphs.
Nodes are descendant sets, and edges are tree edges.

Combine all of the bootstrap trees into a graph.
Can also combine morphology and taxonomy.

"Synthesis"-- order types of trees according to reliability.

## Sarver, Brice A. J.; Hunter, Samuel S.; Settles, Matthew L.: Trials and tribulations of mitochondrial genome assembly using next-generation sequencing data: differences among four bioinformatic workflows

## Gilchrist, Michael; Hewgley, W. P.; Jian, Huang; Zaretzki, Russell: A General Bayesian Approach for Fitting Evolutionary Models to Data: Nesting Simulations within an MCMC Algorithm

Likelihood estimate based on evolutionary simulation of population on its fitness landscape.

Here evolutionary models = trait values.


## Ishikawa, Sohta; Inagaki, Yuji; Hashimoto, Testuo; Sato, Mitsuhisa:	Efficient parallelization of the maximum-likelihood phylogenetic inference with the non-homogeneous substitution model

Parallelize nhML implementing GG98 model using MPI and OpenMP.
They get nearly linear speedup with number of cores.


## Settles, Matt; Sarver, Brice A. J.; Hardwick, Kayla Michelle; Zhbannikov, Ilya; Hunter, Sam: A New Approach to Targeted Next Generation Sequence Assembly using ARC: Assembly by Reduced Complexity

Pipeline-- map using Bowtie2 or Blat with "sloppy parameters.
Extract mapped reads into target bins
Assemble each target individually
Replace targets with assembled contigs
Repeat.
