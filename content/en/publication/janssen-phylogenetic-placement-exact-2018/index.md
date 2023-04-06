---
# Documentation: https://sourcethemes.com/academic/docs/managing-content/

title: Phylogenetic Placement of Exact Amplicon Sequences Improves Associations with
  Clinical Information
subtitle: ''
summary: ''
authors:
- Stefan Janssen
- Daniel McDonald
- Antonio Gonzalez
- Jose A. Navas-Molina
- Lingjing Jiang
- Zhenjiang Zech Xu
- Kevin Winker
- Deborah M. Kado
- Eric Orwoll
- Mark Manary
- Siavash Mirarab
- Rob Knight
tags: []
categories: []
date: '2018-06-01'
lastmod: 2023-04-06T10:33:47Z
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
publishDate: '2023-04-06T12:05:11.298506Z'
publication_types:
- '2'
abstract: Recent algorithmic advances in amplicon-based microbiome studies enable
  the inference of exact amplicon sequence fragments. These new methods enable the
  investigation of sub-operational taxonomic units (sOTU) by removing erroneous sequences.
  However, short (e.g., 150-nucleotide [nt]) DNA sequence fragments do not contain
  sufficient phylogenetic signal to reproduce a reasonable tree, introducing a barrier
  in the utilization of critical phylogenetically aware metrics such as Faith's PD
  or UniFrac. Although fragment insertion methods do exist, those methods have not
  been tested for sOTUs from high-throughput amplicon studies in insertions against
  a broad reference phylogeny. We benchmarked the SATé-enabled phylogenetic placement
  (SEPP) technique explicitly against 16S V4 sequence fragments and showed that it
  outperforms the conceptually problematic but often-used practice of reconstructing
  de novo phylogenies. In addition, we provide a BSD-licensed QIIME2 plugin (https://github.com/biocore/q2-fragment-insertion)
  for SEPP and integration into the microbial study management platform QIITA. IMPORTANCE
  The move from OTU-based to sOTU-based analysis, while providing additional resolution,
  also introduces computational challenges. We demonstrate that one popular method
  of dealing with sOTUs (building a de novo tree from the short sequences) can provide
  incorrect results in human gut metagenomic studies and show that phylogenetic placement
  of the new sequences with SEPP resolves this problem while also yielding other benefits
  over existing methods.
publication: '*mSystems*'
doi: 10.1128/mSystems.00021-18
---
