---
url_pdf: ""
summary: A basic expectation-maximization algorithm to estimate parameters of binomial mixtures.
authors:
  - admin
url_video: ""
date: 2021-01-01T00:00:00Z
categories: []
external_link: ""
url_slides: ""
title: EM Algorithm for Mixture Model
tags:
  - expectation-maximization algorithm
  - binomial distribution
  - mixture model
  - coin flip
links: null
image:
  caption: null
  filename: featured
  focal_point: Smart
  preview_only: false
url_code: "https://github.com/ianarriagamackenzie/emalgo_binommix"
---

We can generate a 'population' for a binomial mixture under the following assumptions: That we have a number *n* of true cases out of a possible number *N* total, and that these have a binomial distribution with {{< math >}}$\pi_i${{< /math >}} probability of being from each distribution.

This is easier to visualize with a 'coins in a pot' example. Say we have a pot filled with two types of coins, each type of coin having its own probability of heads. We pull a number of coins *S* from the pot, flip each coin *N* times and record the number of *n* heads. Under these assumptions, the probability of seeing *n* heads for each coin would be:

{{< math >}}
$$
P \left( n \vert N, \Theta \right) = \pi_1 \mbox{Binom} \left( n \vert N, \theta_1 \right) + \pi_2 \mbox{Binom} \left( n \vert N, \theta_2 \right)
$$
{{< /math >}}

or more generally for *K* different types of coins 

{{< math >}}
$$
$$ P \left( n \vert N, \Theta \right) = \sum_{k=1}^{K} \pi_k \mbox{Binom} \left( n \vert N, \theta_k \right) $$
$$
{{< /math >}}