---
title: Lebesgue Decomposition of Probability Distributions
description: A formal definition of the three types of probability distributions and the statement and proof of the Lebesgue Decomposition Theorem.
---

**Types of Distributions.**

**Definition.**
A probability measure $P$ on the measurable space $(\mathbb{R}, \mathcal{B}(\mathbb{R}))$ is ***absolutely continuous*** with respect to the Lebesgue measure $\lambda$, denoted $P \ll \lambda$, if for every set $A \in \mathcal{B}(\mathbb{R})$ with $\lambda(A)=0$, it follows that $P(A)=0$.

**Theorem.**
A probability measure $P$ is absolutely continuous with respect to $\lambda$ if and only if there exists a non-negative, integrable function $f: \mathbb{R} \to [0, \infty)$, called the probability density function (PDF), such that for every $A \in \mathcal{B}(\mathbb{R})$:
$$
P(A) = \int_A f(x) \,d\lambda(x)
$$

**Example.**
The Normal distribution $\mathcal{N}(\mu, \sigma^2)$ is absolutely continuous, with PDF $f(x) = \frac{1}{\sigma\sqrt{2\pi}} \exp\left(-\frac{(x-\mu)^2}{2\sigma^2}\right)$.

**Definition.**
A probability measure $P$ on $(\mathbb{R}, \mathcal{B}(\mathbb{R}))$ is ***discrete*** if there exists a countable set $S \subset \mathbb{R}$ such that $P(S)=1$.

**Theorem.**
A probability measure $P$ is discrete if and only if it can be represented by a probability mass function (PMF) $p: S \to [0, 1]$ on a countable set $S$, where $p(x) = P(\{x\})$ for each $x \in S$, and $\sum_{x \in S} p(x) = 1$.

**Example.**
The Poisson distribution $\operatorname{Pois}(\lambda)$ is discrete, supported on the set of non-negative integers $S = \{0, 1, 2, \dots\}$, with PMF $p(k) = \frac{\lambda^k e^{-\lambda}}{k!}$.

**Definition.**
A probability measure $P$ on $(\mathbb{R}, \mathcal{B}(\mathbb{R}))$ is ***singular*** with respect to the Lebesgue measure $\lambda$, denoted $P \perp \lambda$, if there exists a set $S \in \mathcal{B}(\mathbb{R})$ with $\lambda(S)=0$ such that $P(S)=1$. A probability measure is ***singular continuous*** if it is singular with respect to $\lambda$ and its cumulative distribution function (CDF) $F(x) = P((-\infty, x])$ is continuous.

**Theorem.**
A probability measure $P$ with CDF $F$ is singular continuous if and only if $F$ is a continuous function and its derivative $F'$ exists and is zero almost everywhere with respect to $\lambda$.

**Example.**
The Cantor distribution is singular continuous. Its CDF is the Cantor function, which is continuous and has a derivative of zero almost everywhere, yet it is not constant. The distribution is concentrated on the Cantor set, which has Lebesgue measure zero.

**The Lebesgue Decomposition Theorem.**

**Theorem.**
Let $P$ be a probability measure on $(\mathbb{R}, \mathcal{B}(\mathbb{R}))$. Then there exists a unique convex combination
$$
P = \alpha_1 P_{ac} + \alpha_2 P_d + \alpha_3 P_{sc}
$$
where $P_{ac}$ is an absolutely continuous probability measure, $P_d$ is a discrete probability measure, and $P_{sc}$ is a singular continuous probability measure. The coefficients $\alpha_1, \alpha_2, \alpha_3$ are non-negative and sum to 1.

***Proof of Existence.***
Let $P$ be a probability measure and $F$ its CDF. Let $D$ be the countable set of discontinuity points of $F$.
Define a measure $P_d$ by $P_d(A) = P(A \cap D)$ for any $A \in \mathcal{B}(\mathbb{R}))$. Let $\alpha_2 = P(D)$. If $\alpha_2 > 0$, let $\bar{P}_d(A) = P_d(A)/\alpha_2$ be the corresponding discrete probability measure. If $\alpha_2 = 0$, $P_d$ is the zero measure.
Define a measure $P_c$ by $P_c(A) = P(A \cap D^c)$. The measure $P_c$ has a continuous CDF and $P = P_d + P_c$.
By the Radon-Nikodym theorem, the measure $P_c$ can be decomposed with respect to the Lebesgue measure $\lambda$ into an absolutely continuous part $\mu_{ac}$ and a singular part $\mu_{sc}$, such that $P_c = \mu_{ac} + \mu_{sc}$, with $\mu_{ac} \ll \lambda$ and $\mu_{sc} \perp \lambda$.
The singular measure $\mu_{sc}$ corresponds to a continuous CDF since $P_c$ does. Thus, $\mu_{sc}$ is a singular continuous measure.
Let $\alpha_1 = \mu_{ac}(\mathbb{R})$ and $\alpha_3 = \mu_{sc}(\mathbb{R})$. If $\alpha_1 > 0$, let $\bar{P}_{ac}(A) = \mu_{ac}(A)/\alpha_1$. If $\alpha_3 > 0$, let $\bar{P}_{sc}(A) = \mu_{sc}(A)/\alpha_3$.
The decomposition is $P = \mu_{ac} + P_d + \mu_{sc} = \alpha_1 \bar{P}_{ac} + \alpha_2 \bar{P}_d + \alpha_3 \bar{P}_{sc}$.
The coefficients sum to unity: $\alpha_1 + \alpha_2 + \alpha_3 = \mu_{ac}(\mathbb{R}) + P_d(\mathbb{R}) + \mu_{sc}(\mathbb{R}) = P_c(\mathbb{R}) + P_d(\mathbb{R}) = P(\mathbb{R}) = 1$.
This establishes the existence of the decomposition.
$\square$

***Proof of Uniqueness.***
Suppose $P = \alpha_1 P_1 + \alpha_2 P_2 + \alpha_3 P_3 = \beta_1 Q_1 + \beta_2 Q_2 + \beta_3 Q_3$ are two such decompositions.
The discrete part of $P$ is concentrated on a countable set. For any point $x \in \mathbb{R}$, $P(\{x\}) = \alpha_2 P_2(\{x\}) = \beta_2 Q_2(\{x\})$.
Summing over all $x \in \mathbb{R}$ yields $\alpha_2 \sum P_2(\{x\}) = \beta_2 \sum Q_2(\{x\})$, which implies $\alpha_2 = \beta_2$. If $\alpha_2 > 0$, it follows that $P_2 = Q_2$.
Let $\mu_1 = \alpha_1 P_1$, $\mu_3 = \alpha_3 P_3$, $\nu_1 = \beta_1 Q_1$, and $\nu_3 = \beta_3 Q_3$. The equality of the discrete parts implies $\mu_1 + \mu_3 = \nu_1 + \nu_3$.
Rearranging gives $\mu_1 - \nu_1 = \nu_3 - \mu_3$.
The measure $\mu_1 - \nu_1$ is absolutely continuous with respect to $\lambda$. The measure $\nu_3 - \mu_3$ is singular with respect to $\lambda$.
A measure that is both absolutely continuous and singular with respect to $\lambda$ must be the zero measure.
Therefore, $\mu_1 - \nu_1 = 0$ and $\nu_3 - \mu_3 = 0$, implying $\mu_1 = \nu_1$ and $\mu_3 = \nu_3$.
From $\mu_1 = \nu_1$, evaluating the total measure gives $\alpha_1 = \beta_1$. If $\alpha_1 > 0$, then $P_1 = Q_1$.
Similarly, $\mu_3 = \nu_3$ implies $\alpha_3 = \beta_3$, and if $\alpha_3 > 0$, then $P_3 = Q_3$.
The decomposition is unique.
$\square$