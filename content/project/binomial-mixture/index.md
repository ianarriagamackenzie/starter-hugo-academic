---
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
url_pdf: "BinonMix_Ancestry_Supp.pdf"
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
P \left( n \vert N, \Theta \right) = \sum_{k=1}^{K} \pi_k \mbox{Binom} \left( n \vert N, \theta_k \right)
$$
{{< /math >}}

where {{< math >}}$\theta_k${{< /math >}} is the probability of heads for each type of coin. Therefor the log-likelihood for our parameters is:

{{< math >}}
$$
\mathcal{L} \left( \Theta \vert X, Z \right) = ln P \left( X, Z \vert \Theta \right)
$$
{{< /math >}}

Where {{< math >}}$\Theta_k${{< /math >}} represents the set of {{< math >}}$\pi_k, \theta_k${{< /math >}}, *X* represents the set of heads and total coin flips, and *Z* represents the set of coin proportions and heads proportions. So the Auxiliary Function is:

{{< math >}}
$$
Q(\Theta, \Theta_o) = E \left[ ln \mathcal{L} \left( \Theta \vert X, Z \right) \vert X, \Theta_o \right]
$$
{{< /math >}}

and our expectation is:

{{< math >}}
$$
E \left[ ln P \left( X, Z, \vert \Theta \right) \vert X, \Theta_o \right] = \sum_{z_i = 1}^K ln P \left( n_i, z_i \vert \Theta \right) \cdot P \left( z_i \vert n_i, \Theta_o \right)
$$
{{< /math >}}

where

{{< math >}}
$$
P \left( z_i = k \vert n_i , \Theta_o \right) = \dfrac{P \left( z_i = k , n_i \vert \Theta_o \right)}{P \left( \vert \Theta_o \right)} = \dfrac{\pi_{k,o} \mbox{Binom} \left( n_i \vert N_i , \theta_{k,o} \right)}{\sum_{l=1}^{K} \pi_{l,o} \mbox{Binom} \left( n_i \vert N_i , \theta_{l,o} \right)}
$$
{{< /math >}}

We can then use the following expressions to update {{< math >}}$\pi${{< /math >}} and {{< math >}}$\theta${{< /math >}} until convergence.

{{< math >}}
$$
\pi_m = \dfrac{1}{S} \sum_{i=1}^S P \left( z_i = m \vert n_i , \Theta_{o} \right)
$$
{{< /math >}}

{{< math >}}
$$
\theta_{m,S} = \dfrac{\sum_{i=1}^S n_i \cdot P \left( z_i = m \vert n_i , \Theta_{o} \right)}{\sum_{j=1}^S N_j \cdot P \left( z_j = m \vert n_j , \Theta_{o} \right)}
$$
{{< /math >}}