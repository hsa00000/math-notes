---
title: Order‑Theoretic Limsup and Liminf
description: Introduce the general concept of limsup and liminf that applies to both the case of sequence of numbers and sequence of sets.
---

**Definition (Complete lattice).**  
A partially ordered set $(L,\le)$ is called a _complete lattice_ if for every $S\subseteq L$, the supremum $\sup S$ and infimum $\inf S$ exists in $L$.

**Definition (Order‑theoretic limits).**  
Let $(L,\le)$ be a complete lattice and $\{x_n\}\subseteq L$ be a sequence in $L$. Define the _upper‑tail suprema_ and _lower‑tail infima_ of $\{x_n\}$ by

$$
s_n := \operatorname*{sup}_{m\ge n} x_m,
\qquad
i_n := \operatorname*{inf}_{m\ge n} x_m.
$$

Define the _limit suprema_ and _limit infima_ by

$$
\operatorname*{limsup}_{n\to\infty} x_n := \operatorname*{inf}_{n} s_n,
\quad
\operatorname*{liminf}_{n\to\infty} x_n := \operatorname*{sup}_{n} i_n.
$$

**Definition (limsup and liminf of sequence of numbers).**  
Taking $L = [-\infty,\infty]$ with the usual order recovers the classical limsup and liminf for sequences of real numbers.

**Definition (limsup and liminf of sequence of sets).**  
Let $X$ be a set. Taking $L = \mathcal P(X)$ ordered by inclusion reproduces the limsup and liminf of sequence of sets

$$
\operatorname*{limsup}_{n\to\infty} A_n
    = \bigcap_{N=1}^{\infty} \bigcup_{n\ge N} A_n,
\qquad
\operatorname*{liminf}_{n\to\infty} A_n
    = \bigcup_{N=1}^{\infty} \bigcap_{n\ge N} A_n.
$$
