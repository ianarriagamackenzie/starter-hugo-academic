---
summary: The log-likelihood can be maximized under an assumption of a binomial mixture to infer ancestry.
authors:
  - admin
url_video: ""
date: 2021-05-01T00:00:00Z
categories: []
external_link: ""
url_slides: ""
title: Binomial Distribution of Allele Data
tags:
  - log-likelihood
  - binomial distribution
  - mixture model
  - gradient descent
  - genetics
links: null
image:
  caption: null
  filename: featured
  focal_point: Smart
  preview_only: false
url_code: "https://github.com/ianarriagamackenzie/binomdist_popallele"
url_pdf: "/project/binomial-distribution-of-allele-data/BinomMix_Ancestry_Supp.pdf"
---

Summary population allele data can be modeled using a binomial mixture distribtion with homogeneous reference populations. Here we show an example of this using the gnomAD V2.1 African/African-American data set, and homogeneous African and European reference panels from 1000 Genomes. We adopt the following model:

{{< math >}}
$$
P \left( n \vert N, \Theta \right) = \mbox{Binom} \left( n \bigg\vert N, \sum_{k=1}^{K} \pi_k \theta_k \right)
$$
{{< /math >}}

{{< math >}}
$$
\ell( \Theta ) = ln \mathcal{L} (\Theta \vert X) = \sum_{i=1}^S ln \left[ \mbox{Binom} \left( n \bigg\vert N, \sum_{k=1}^{K} \pi_k \theta_k \right) \right]
$$
{{< /math >}}

where 

*S* is the set of SNPs

*K* are ancestries

{{< math >}}$\pi_k${{< /math >}} are ancestry proportions for *k*

{{< math >}}$n_i${{< /math >}} is the Allele Count for that SNP

{{< math >}}$N_i${{< /math >}} is the Allele Number for that SNP

{{< math >}}$\theta_k${{< /math >}} is the Allele Frequency for that SNP

This leads to the above image which shows a maximation of the log likelihood at the following values