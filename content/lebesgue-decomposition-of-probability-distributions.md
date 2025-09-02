---
title: Lebesgue Decomposition of Probability Distributions
description: A formal definition of the three types of probability distributions and the statement and proof of the Lebesgue Decomposition Theorem.
date: 2025-09-02
---

**Types of Distributions.**

**Definition (Absolutely Continuous Measure).**
Let $P$ and $\lambda$ be measures on a measurable space $(\Omega, \mathcal{F})$. The measure $P$ is **_absolutely continuous_** with respect to $\lambda$, denoted $P \ll \lambda$, if for every set $A \in \mathcal{F}$ with $\lambda(A)=0$, it follows that $P(A)=0$.

**Theorem (Radon-Nikodym for Probability Measures).**
A probability measure $P$ on $(\mathbb{R}, \mathcal{B}(\mathbb{R}))$ is absolutely continuous with respect to the Lebesgue measure $\lambda$ if and only if there exists a non-negative, integrable function $f: \mathbb{R} \to [0, \infty)$, called the probability density function (PDF), such that for every $A \in \mathcal{B}(\mathbb{R})$:

$$
P(A) = \int_A f(x) \,d\lambda(x)
$$

_Proof._
($\Leftarrow$) Assume there exists such a function $f$. If $\lambda(A)=0$, then the integral $\int_A f(x) \,d\lambda(x)$ is zero by properties of the Lebesgue integral. Thus, $P(A)=0$, which implies $P \ll \lambda$.

($\Rightarrow$) Assume $P \ll \lambda$. Since $P$ is a finite measure (as $P(\mathbb{R})=1$) and $\lambda$ is a $\sigma$-finite measure, the Radon-Nikodym theorem guarantees the existence of a non-negative, measurable function $f$ such that $P(A) = \int_A f(x) \,d\lambda(x)$ for all $A \in \mathcal{B}(\mathbb{R})$. This function $f$ is the Radon-Nikodym derivative $dP/d\lambda$.
$\square$

**Definition (Discrete Measure).**
A probability measure $P$ on $(\mathbb{R}, \mathcal{B}(\mathbb{R}))$ is **_discrete_** if there exists a countable set $S \subset \mathbb{R}$ such that $P(S)=1$. The points in $S$ with $P(\{x\}) > 0$ are called atoms.

**Theorem (Discrete Measure Representation).**
A probability measure $P$ is discrete if and only if it can be represented by a probability mass function (PMF) $p: S \to [0, 1]$ on a countable set $S$, where $p(x) = P(\{x\})$ for each $x \in S$, and $\sum_{x \in S} p(x) = 1$.

_Proof._
($\Rightarrow$) Let $P$ be a discrete measure concentrated on a countable set $S$. Define $p(x) = P(\{x\})$ for each $x \in S$. By the countable additivity of $P$, we have

$$
P(S) = \sum_{x \in S} P(\{x\}) = \sum_{x \in S} p(x)
$$

Since $P(S)=1$, it follows that $\sum_{x \in S} p(x)=1$.

($\Leftarrow$) Given a countable set $S$ and a function $p: S \to [0, 1]$ with $\sum_{x \in S} p(x)=1$, define a measure $P$ for any $A \in \mathcal{B}(\mathbb{R})$ by $P(A) = \sum_{x \in A \cap S} p(x)$. This function $P$ is a probability measure, and since $P(S) = \sum_{x \in S \cap S} p(x) = 1$, it is a discrete measure.
$\square$

**Definition (Singular and Singular Continuous Measures).**
Two measures $P$ and $\lambda$ on $(\Omega, \mathcal{F})$ are **_mutually singular_**, denoted $P \perp \lambda$, if there exist disjoint sets $A, B \in \mathcal{F}$ with $A \cup B = \Omega$ such that $P(B)=0$ and $\lambda(A)=0$. For a probability measure $P$ on $(\mathbb{R}, \mathcal{B}(\mathbb{R}))$, this is equivalent to the existence of a set $S \in \mathcal{B}(\mathbb{R})$ with $\lambda(S)=0$ such that $P(S)=1$. A probability measure is **_singular continuous_** if it is singular with respect to $\lambda$ and its cumulative distribution function (CDF) $F(x) = P((-\infty, x])$ is continuous.

**Definition (Cantor Distribution).**
The **_Cantor distribution_** is the probability measure $P_C$ whose CDF is the Cantor function $c(x)$. The Cantor function is a continuous, non-decreasing function on $[0, 1]$ with $c(0)=0$ and $c(1)=1$. It is constructed in relation to the Cantor set $C$, which is an uncountable set of Lebesgue measure zero. The function $c(x)$ has a derivative that exists and is equal to zero almost everywhere. The measure $P_C$ is concentrated entirely on the Cantor set $C$, so $P_C(C)=1$ while $\lambda(C)=0$, making it a singular continuous distribution.

**Theorem (Characterization of Singular Continuous Measures).**
A probability measure $P$ with CDF $F$ is singular continuous if and only if $F$ is a continuous function and its derivative $F'$ exists and is zero almost everywhere with respect to $\lambda$.

_Proof._
Let $P$ be a probability measure on $(\mathbb{R}, \mathcal{B}(\mathbb{R}))$. By the Lebesgue Decomposition Theorem relative to the Lebesgue measure $\lambda$, $P$ can be uniquely written as $P = P_{ac} + P_s$, where $P_{ac} \ll \lambda$ and $P_s \perp \lambda$. The CDF $F$ of $P$ is likewise a sum $F = F_{ac} + F_s$, where $F_{ac}$ and $F_s$ are the CDFs of $P_{ac}$ and $P_s$, respectively. By the Radon-Nikodym theorem, there exists a density $f = dP_{ac}/d\lambda$ such that $F_{ac}(x) = \int_{-\infty}^x f(t) d\lambda(t)$. A fundamental result of measure theory states that $F'(x)$ exists $\lambda$-a.e. and is given by $F'(x) = f(x) + F_s'(x)$. Furthermore, the derivative of the CDF of a singular measure is zero $\lambda$-a.e., so $F_s'(x)=0$ a.e. This establishes that $F'(x) = f(x)$ for $\lambda$-almost all $x$.

($\Rightarrow$) Assume $P$ is singular continuous. By definition, its CDF $F$ is continuous. Also by definition, $P$ is singular with respect to $\lambda$. In the decomposition $P = P_{ac} + P_s$, the singularity of $P$ implies that its absolutely continuous component $P_{ac}$ must be the zero measure. Consequently, the density $f = dP_{ac}/d\lambda$ must be the zero function a.e. Since $F'(x) = f(x)$ a.e., it follows that $F'(x) = 0$ a.e.

($\Leftarrow$) Assume $F$ is continuous and $F'(x)=0$ for $\lambda$-almost all $x$. The density of the absolutely continuous part of $P$ is given by $f(x) = F'(x)$ a.e. By assumption, $F'(x)=0$ a.e., so $f(x)=0$ a.e. This implies that the absolutely continuous measure $P_{ac}$ is the zero measure, since

$$
P_{ac}(A) = \int_A f(x) d\lambda(x) = 0
$$

for all $A$. Therefore, the decomposition of $P$ is $P = 0 + P_s = P_s$, which shows that $P$ is purely singular. Since $P$ is singular and has a continuous CDF, it is by definition singular continuous.
$\square$

**The Lebesgue Decomposition Theorem.**

**Theorem (Lebesgue Decomposition for Probability Measures).**
Let $P$ be a probability measure on $(\mathbb{R}, \mathcal{B}(\mathbb{R}))$. Then there exists a unique decomposition of $P$ into a convex combination

$$
P = \alpha_1 P_{ac} + \alpha_2 P_d + \alpha_3 P_{sc}
$$

where $P_{ac}$ is an absolutely continuous probability measure, $P_d$ is a discrete probability measure, and $P_{sc}$ is a singular continuous probability measure. The coefficients $\alpha_1, \alpha_2, \alpha_3$ are non-negative and sum to 1.

_Proof._
**Existence.** Let $F$ be the CDF of $P$. Let $D$ be the set of discontinuity points of $F$. $D$ is countable because for any integer $n \ge 1$, the set of points with jump size greater than $1/n$ is finite. $D$ is the union of these sets over all $n \in \mathbb{N}$. Define a measure $P'_d$ by $P'_d(A) = P(A \cap D)$ for any $A \in \mathcal{B}(\mathbb{R})$. Let

$$
\alpha_2 = P(D) = P'_d(\mathbb{R})
$$

If $\alpha_2 > 0$, let $P_d(A) = P'_d(A) / \alpha_2$ be the corresponding discrete probability measure. If $\alpha_2 = 0$, $P$ has no discrete part. Define a measure $P'_c$ by $P'_c(A) = P(A \cap D^c)$. The CDF of $P'_c$ is continuous because all jumps in $F$ occurred on the set $D$, which has been excluded. By the standard Lebesgue decomposition theorem, $P'_c$ can be uniquely decomposed with respect to the Lebesgue measure $\lambda$ into an absolutely continuous part $P'_{ac}$ and a singular part $P'_{sc}$, such that $P'_c = P'_{ac} + P'_{sc}$ with $P'_{ac} \ll \lambda$ and $P'_{sc} \perp \lambda$. Since the CDF of $P'_c$ is continuous, the CDFs of its components $P'_{ac}$ and $P'_{sc}$ must also be continuous. Thus, $P'_{sc}$ corresponds to a singular continuous measure. Let $\alpha_1 = P'_{ac}(\mathbb{R})$ and $\alpha_3 = P'_{sc}(\mathbb{R})$. If $\alpha_1 > 0$, define $P_{ac}(A) = P'_{ac}(A) / \alpha_1$. If $\alpha_3 > 0$, define $P_{sc}(A) = P'_{sc}(A) / \alpha_3$. The decomposition is

$$
P = P'_d + P'_c = P'_d + P'_{ac} + P'_{sc}
$$

This can be written as $P = \alpha_1 P_{ac} + \alpha_2 P_d + \alpha_3 P_{sc}$ (where if $\alpha_i=0$, the corresponding measure term is zero). The coefficients sum to one:

$$
\begin{align*}
\alpha_1 + \alpha_2 + \alpha_3 &= P'_{ac}(\mathbb{R}) + P'_{sc}(\mathbb{R}) + P'_d(\mathbb{R}) \\
&= P'_c(\mathbb{R}) + P'_d(\mathbb{R}) \\
&= P(D^c) + P(D) \\
&= P(\mathbb{R}) = 1
\end{align*}
$$

This establishes existence.
**Uniqueness.** Suppose

$$
P = \alpha_1 P_1 + \alpha_2 P_2 + \alpha_3 P_3 = \beta_1 Q_1 + \beta_2 Q_2 + \beta_3 Q_3
$$

are two such decompositions. The discrete part of a measure is uniquely determined by its values on singletons. For any $x \in \mathbb{R}$, $P(\{x\}) = \alpha_2 P_2(\{x\})$ and also $P(\{x\}) = \beta_2 Q_2(\{x\})$. Let $S$ be the countable set of all atoms of $P$. Then

$$
\alpha_2 = P(S) = \sum_{x \in S} P(\{x\}) = \beta_2
$$

If $\alpha_2 > 0$, then $P_2(A) = P(A \cap S) / \alpha_2$ and $Q_2(A) = P(A \cap S) / \beta_2$, which implies $P_2 = Q_2$. The equality of the discrete parts implies $\alpha_1 P_1 + \alpha_3 P_3 = \beta_1 Q_1 + \beta_3 Q_3$. Let this measure be $\mu_c$. This measure is continuous (has no atoms). By the uniqueness of the standard Lebesgue decomposition of $\mu_c$ with respect to $\lambda$, its absolutely continuous and singular parts are unique. The absolutely continuous part is $\alpha_1 P_1 = \beta_1 Q_1$, and the singular part is $\alpha_3 P_3 = \beta_3 Q_3$. Taking the total measure of the absolutely continuous part gives $\alpha_1 P_1(\mathbb{R}) = \beta_1 Q_1(\mathbb{R})$, which implies $\alpha_1 = \beta_1$. If $\alpha_1 > 0$, then $P_1 = Q_1$. Similarly, taking the total measure of the singular part gives $\alpha_3 = \beta_3$. If $\alpha_3 > 0$, then $P_3 = Q_3$. The decomposition is unique.
$\square$

**Corollary (Decomposition of Random Variables).**
For any real-valued random variable $X$, its cumulative distribution function $F_X$ can be uniquely written as a convex combination

$$
F_X(x) = \alpha_1 F_{ac}(x) + \alpha_2 F_d(x) + \alpha_3 F_{sc}(x)
$$

where $F_{ac}$, $F_d$, and $F_{sc}$ are the CDFs of an absolutely continuous, a discrete, and a singular continuous probability distribution, respectively, and $\alpha_1, \alpha_2, \alpha_3$ are non-negative coefficients summing to 1.

_Proof._
A random variable $X$ induces a probability measure $P_X$ on $(\mathbb{R}, \mathcal{B}(\mathbb{R}))$ via $P_X(A) = P(X \in A)$. By the Lebesgue Decomposition Theorem, $P_X$ has a unique decomposition $P_X = \alpha_1 P_{ac} + \alpha_2 P_d + \alpha_3 P_{sc}$. The CDF of $X$ is $F_X(x) = P_X((-\infty, x])$. Applying this to the decomposition gives

$$
F_X(x) = \alpha_1 P_{ac}((-\infty, x]) + \alpha_2 P_d((-\infty, x]) + \alpha_3 P_{sc}((-\infty, x])
$$

This is precisely $F_X(x) = \alpha_1 F_{ac}(x) + \alpha_2 F_d(x) + \alpha_3 F_{sc}(x)$, where $F_{ac}$, $F_d$, and $F_{sc}$ are the CDFs corresponding to the measures $P_{ac}$, $P_d$, and $P_{sc}$. The uniqueness of the CDF decomposition follows directly from the uniqueness of the measure decomposition.
$\square$
