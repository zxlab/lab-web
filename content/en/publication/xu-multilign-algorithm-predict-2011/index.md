---
# Documentation: https://sourcethemes.com/academic/docs/managing-content/

title: 'Multilign: An Algorithm to Predict Secondary Structures Conserved in Multiple
  RNA Sequences'
subtitle: ''
summary: ''
authors:
- Zhenjiang Xu
- David H. Mathews
tags: []
categories: []
date: '2011-03-01'
lastmod: 2023-04-06T10:33:52Z
featured: false
draft: false

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
# Focal points: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight.
image:
  caption: ''
  focal_point: ''
  preview_only: false

# Projects (optional).
#   Associate this post with one or more of your projects.
#   Simply enter your project's folder or file name without extension.
#   E.g. `projects = ["internal-project"]` references `content/project/deep-learning/index.md`.
#   Otherwise, set `projects = []`.
projects: []
publishDate: '2023-04-06T12:05:15.416077Z'
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
publication: '*Bioinformatics*'
doi: 10.1093/bioinformatics/btq726
---
