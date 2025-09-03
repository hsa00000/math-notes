---
title: Lebesgue Decomposition of Probability Distributions II (The CDF Approach)
description: A decomposition of cumulative distribution functions into discrete, absolutely continuous, and singular continuous components, presented using the language of calculus without explicit measure theory.
---

**Types of Distributions.**

**Definition (Absolutely Continuous Distribution).**
A cumulative distribution function (CDF) $F(x)$ represents an ***absolutely continuous distribution*** if there exists a non-negative, integrable function $f(x)$, called the probability density function (PDF), such that for all $x \in \mathbb{R}$,

$$
F(x) = \int_{-\infty}^x f(t) \,dt
$$

An absolutely continuous CDF is continuous everywhere and differentiable almost everywhere, with its derivative being the PDF, $F'(x) = f(x)$ a.e.

**Definition (Discrete Distribution).**
A CDF $F(x)$ represents a ***discrete distribution*** if it is a step function that increases only by a countable number of finite jumps. If the jump points are the countable set $S = \{x_1, x_2, \ldots \}$, then $F(x)$ can be written as

$$
F(x) = \sum_{x_k \in S, x_k \le x} p_k
$$

where $p_k = F(x_k) - \lim_{y \to x_k^-} F(y)$ is the jump size at $x_k$, and $\sum_{k} p_k = 1$.

**Definition (Singular Continuous Distribution).**
A CDF $F(x)$ represents a ***singular continuous distribution*** if it satisfies two conditions:
1. $F(x)$ is continuous for all $x \in \mathbb{R}$.
2. Its derivative exists and is zero almost everywhere, i.e., $F'(x) = 0$ for all $x$ except for a set of Lebesgue measure zero.

The Cantor function is the canonical example of a singular continuous CDF.

**The Lebesgue Decomposition Theorem.**

**Theorem (Lebesgue Decomposition for CDFs).**
Any cumulative distribution function $F(x)$ can be uniquely decomposed into a convex combination

$$
F(x) = \alpha_1 F_{ac}(x) + \alpha_2 F_d(x) + \alpha_3 F_{sc}(x)
$$

where $F_{ac}$ is an absolutely continuous CDF, $F_d$ is a discrete CDF, and $F_{sc}$ is a singular continuous CDF. The coefficients $\alpha_1, \alpha_2, \alpha_3$ are non-negative and sum to 1.

*Proof.*
**Existence.**
Let $F(x)$ be an arbitrary CDF. The proof proceeds by construction in two steps.

1.  **Extracting the Discrete Part.** Let $D = \{x_1, x_2, \dots\}$ be the set of discontinuity points of $F$. This set is countable. For each $x_k \in D$, define the jump size $p_k = F(x_k) - \lim_{y \to x_k^-} F(y)$. Construct the function $F'_d(x) = \sum_{x_k \in D, x_k \le x} p_k$. Let $\alpha_2 = \lim_{x \to \infty} F'_d(x) = \sum_{k} p_k$. If $\alpha_2 > 0$, define the discrete CDF $F_d(x) = \frac{1}{\alpha_2}F'_d(x)$. If $\alpha_2=0$, the distribution has no discrete part. Now define the continuous part of $F$ as $F_c(x) = F(x) - F'_d(x)$. The function $F_c(x)$ is continuous because all jumps of $F$ have been subtracted out. It is also non-decreasing.

2.  **Decomposing the Continuous Part.** Any non-decreasing function like $F_c(x)$ is differentiable almost everywhere. Let its derivative be $f_c(x) = F_c'(x)$. The function $f_c(x)$ is non-negative and integrable. We can now define the absolutely continuous component of $F_c(x)$ by integrating its derivative:

    $$
    F'_{ac}(x) = \int_{-\infty}^x f_c(t) \,dt = \int_{-\infty}^x F_c'(t) \,dt
    $$

    Next, define the singular continuous component as the remainder: $F'_{sc}(x) = F_c(x) - F'_{ac}(x)$. By construction, $F'_{sc}(x)$ is continuous. Its derivative is $F'_{sc}{'}(x) = F_c'(x) - F'_{ac}{'}(x) = f_c(x) - f_c(x) = 0$ almost everywhere. Thus, $F'_{sc}(x)$ corresponds to a singular continuous distribution.

    Let $\alpha_1 = \lim_{x \to \infty} F'_{ac}(x)$ and $\alpha_3 = \lim_{x \to \infty} F'_{sc}(x)$. If $\alpha_1 > 0$, define $F_{ac}(x) = \frac{1}{\alpha_1}F'_{ac}(x)$. If $\alpha_3 > 0$, define $F_{sc}(x) = \frac{1}{\alpha_3}F'_{sc}(x)$. We have constructed the decomposition $F(x) = F'_d(x) + F'_{ac}(x) + F'_{sc}(x) = \alpha_2 F_d(x) + \alpha_1 F_{ac}(x) + \alpha_3 F_{sc}(x)$. The coefficients sum to one:

    $$
    \alpha_1 + \alpha_2 + \alpha_3 = \lim_{x \to \infty} (F'_{ac}(x) + F'_d(x) + F'_{sc}(x)) = \lim_{x \to \infty} F(x) = 1
    $$

This establishes the existence of the decomposition.

**Uniqueness.**
Suppose $F(x) = \alpha_1 F_1 + \alpha_2 F_2 + \alpha_3 F_3$ and $F(x) = \beta_1 G_1 + \beta_2 G_2 + \beta_3 G_3$ are two such decompositions. The set of discontinuities of $F$ and the corresponding jump sizes are uniquely determined by $F$. Only the discrete components contribute to jumps. Thus, the function representing all jumps, $\alpha_2 F_2(x)$, must be identical to $\beta_2 G_2(x)$. Taking the limit as $x \to \infty$ gives $\alpha_2 = \beta_2$. If $\alpha_2 > 0$, then $F_2 = G_2$.

This implies the continuous parts are equal: $F_c(x) = \alpha_1 F_1 + \alpha_3 F_3 = \beta_1 G_1 + \beta_3 G_3$. Differentiating this equation gives $F_c'(x) = \alpha_1 F_1'(x) + \alpha_3 F_3'(x) = \beta_1 G_1'(x) + \beta_3 G_3'(x)$. Since $F_3$ and $G_3$ are singular continuous, $F_3'(x) = G_3'(x) = 0$ almost everywhere. Therefore, $\alpha_1 F_1'(x) = \beta_1 G_1'(x)$ almost everywhere. The absolutely continuous part of a function is uniquely determined by integrating its derivative, so $\alpha_1 F_1(x) = \int_{-\infty}^x \alpha_1 F_1'(t) dt = \int_{-\infty}^x \beta_1 G_1'(t) dt = \beta_1 G_1(x)$. Taking the limit as $x \to \infty$ gives $\alpha_1 = \beta_1$. If $\alpha_1 > 0$, then $F_1 = G_1$. By subtraction, it follows that $\alpha_3 F_3 = \beta_3 G_3$, which implies $\alpha_3 = \beta_3$ and $F_3 = G_3$. The decomposition is unique. $\square$```