---
title: 'Multilign: An Algorithm to Predict Secondary Structures Conserved in Multiple
  RNA Sequences'
_build:
  render: never
  list: never
  publishResources: false
date: '2011-03-01'
publishDate: '2023-04-06T12:14:18.509727Z'
authors:
- Zhenjiang Xu
- David H. Mathews
publication_types:
- '2'
abstract: 'Motivation: With recent advances in sequencing, structural and functional
  studies of RNA lag behind the discovery of sequences. Computational analysis of
  RNA is increasingly important to reveal structure– function relationships with low
  cost and speed. The purpose of this study is to use multiple homologous sequences
  to infer a conserved RNA structure.Results: A new algorithm, called Multilign, is
  presented to find the lowest free energy RNA secondary structure common to multiple
  sequences. Multilign is based on Dynalign, which is a program that simultaneously
  aligns and folds two sequences to find the lowest free energy conserved structure.
  For Multilign, Dynalign is used to progressively construct a conserved structure
  from multiple pairwise calculations, with one sequence used in all pairwise calculations.
  A base pair is predicted only if it is contained in the set of low free energy structures
  predicted by all Dynalign calculations. In this way, Multilign improves prediction
  accuracy by keeping the genuine base pairs and excluding competing false base pairs.
  Multilign has computational complexity that scales linearly in the number of sequences.
  Multilign was tested on extensive datasets of sequences with known structure and
  its prediction accuracy is among the best of available algorithms. Multilign can
  run on long sequences ($>$ 1500 nt) and an arbitrarily large number of sequences.Availability:
  The algorithm is implemented in ANSI C++ and can be downloaded as part of the RNAstructure
  package at: http://rna.urmc.rochester.eduContact: david_mathews@urmc.rochester.eduSupplementary
  information: Supplementary data are available at Bioinformatics online.'
featured: false
publication: '*Bioinformatics*'
doi: 10.1093/bioinformatics/btq726
---

