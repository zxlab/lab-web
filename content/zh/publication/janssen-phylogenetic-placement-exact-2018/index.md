---
title: Phylogenetic Placement of Exact Amplicon Sequences Improves Associations with
  Clinical Information
_build:
  render: never
  list: never
  publishResources: false
date: '2018-06-01'
publishDate: '2023-04-06T12:14:14.126610Z'
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
featured: false
publication: '*mSystems*'
doi: 10.1128/mSystems.00021-18
---

