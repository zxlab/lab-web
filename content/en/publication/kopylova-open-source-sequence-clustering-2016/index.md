---
# Documentation: https://sourcethemes.com/academic/docs/managing-content/

title: Open-Source Sequence Clustering Methods Improve the State Of the Art
subtitle: ''
summary: ''
authors:
- Evguenia Kopylova
- Jose A. Navas-Molina
- Céline Mercier
- Zhenjiang Zech Xu
- Frédéric Mahé
- Yan He
- Hong-Wei Zhou
- Torbjørn Rognes
- J. Gregory Caporaso
- Rob Knight
tags: []
categories: []
date: '2016-02-01'
lastmod: 2023-04-06T10:33:48Z
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
publishDate: '2023-04-06T10:33:47.960015Z'
publication_types:
- '2'
abstract: Sequence clustering is a common early step in amplicon-based microbial community
  analysis, when raw sequencing reads are clustered into operational taxonomic units
  (OTUs) to reduce the run time of subsequent analysis steps. Here, we evaluated the
  performance of recently released state-of-the-art open-source clustering software
  products, namely, OTUCLUST, Swarm, SUMACLUST, and SortMeRNA, against current principal
  options (UCLUST and USEARCH) in QIIME, hierarchical clustering methods in mothur,
  and USEARCH's most recent clustering algorithm, UPARSE. All the latest open-source
  tools showed promising results, reporting up to 60% fewer spurious OTUs than UCLUST,
  indicating that the underlying clustering algorithm can vastly reduce the number
  of these derived OTUs. Furthermore, we observed that stringent quality filtering,
  such as is done in UPARSE, can cause a significant underestimation of species abundance
  and diversity, leading to incorrect biological results. Swarm, SUMACLUST, and SortMeRNA
  have been included in the QIIME 1.9.0 release. IMPORTANCE Massive collections of
  next-generation sequencing data call for fast, accurate, and easily accessible bioinformatics
  algorithms to perform sequence clustering. A comprehensive benchmark is presented,
  including open-source tools and the popular USEARCH suite. Simulated, mock, and
  environmental communities were used to analyze sensitivity, selectivity, species
  diversity (alpha and beta), and taxonomic composition. The results demonstrate that
  recent clustering algorithms can significantly improve accuracy and preserve estimated
  diversity without the application of aggressive filtering. Moreover, these tools
  are all open source, apply multiple levels of multithreading, and scale to the demands
  of modern next-generation sequencing data, which is essential for the analysis of
  massive multidisciplinary studies such as the Earth Microbiome Project (EMP) (J.
  A. Gilbert, J. K. Jansson, and R. Knight, BMC Biol 12:69, 2014, http://dx.doi.org/10.1186/s12915-014-0069-1).
publication: '*mSystems*'
doi: 10.1128/mSystems.00003-15
---
