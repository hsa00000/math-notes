---
title: Measurability of the Derivative
description: A proof that the derivative of a real-valued differentiable function is a measurable function.
date: 2024-05-15T14:30:00+00:00
---

**Theorem (Measurability of the Derivative).**

Let $f: (a, b) \to \mathbb{R}$ be a differentiable function on an open interval $(a,b)$. Then its derivative, $f': (a, b) \to \mathbb{R}$, is a measurable function with respect to the Borel $\sigma$-algebra.

*Proof.*
Let $x \in (a, b)$. By the definition of the derivative,

$$
f'(x) = \lim_{h \to 0} \frac{f(x+h) - f(x)}{h}
$$

We can express this limit using a sequence. For each integer $n \ge 1$, define a sequence of real numbers $h_n = \frac{1}{n}$. For any fixed $x \in (a, b)$, there exists an integer $N_x$ such that for all $n > N_x$, both $x+h_n$ and $x-h_n$ are in $(a,b)$. To avoid issues with the domain boundary for all $x$ simultaneously, we define a sequence of functions $f_n: (a, b) \to \mathbb{R}$ as follows. For each $n \in \mathbb{N}$, choose a sequence of non-zero numbers $\{h_k\}_{k=1}^\infty$ such that $h_k \to 0$ as $k \to \infty$. For instance, let $h_k = 1/k$. For each $k$, define the function $g_k: (a,b) \to \mathbb{R}$ by:

$$
g_k(x) = \frac{f(x+h_k) - f(x)}{h_k}
$$
This function is well-defined for all $x \in (a, b-h_k)$ if $h_k > 0$ or $x \in (a-h_k, b)$ if $h_k < 0$. To simplify the domain, we can extend $f$ to be 0 outside of $(a,b)$ and define for each $n \in \mathbb{N}$ the function $f_n: \mathbb{R} \to \mathbb{R}$ by

$$
f_n(x) = n\left(f\left(x + \frac{1}{n}\right) - f(x)\right)
$$
where we consider $f$ extended to all of $\mathbb{R}$ by setting it to zero outside $(a,b)$.

A differentiable function is continuous. Since $f$ is differentiable on $(a,b)$, it is continuous on $(a,b)$. The extended function may have discontinuities at $a$ and $b$, but since these form a set of measure zero, its measurability is not affected. As a continuous function, $f$ is Borel measurable.

The function $\phi_n(x) = x + 1/n$ is continuous, hence measurable. The composition $f(\phi_n(x)) = f(x+1/n)$ is a composition of measurable functions. Since $f$ is continuous, $f(x+1/n)$ is also measurable.

The function $f_n(x)$ is constructed from the measurable functions $f(x+1/n)$ and $f(x)$ through subtraction and scalar multiplication. The set of measurable functions is closed under linear combinations. Therefore, each function $f_n$ in the sequence is measurable.

By the definition of the derivative, for every $x \in (a,b)$, the sequence of values $\{f_n(x)\}$ converges to $f'(x)$:

$$
\lim_{n \to \infty} f_n(x) = f'(x)
$$

The function $f'$ is the pointwise limit of a sequence of measurable functions $\{f_n\}$. A standard theorem of measure theory states that the pointwise limit of a sequence of measurable functions is itself measurable.

Therefore, $f'$ is a measurable function. $\square$