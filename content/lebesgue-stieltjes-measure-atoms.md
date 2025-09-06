---
title: Lebesgue–Stieltjes Measures and Atoms
description: Relates the continuity of a non-decreasing, right-continuous function G to the atoms of its induced Lebesgue–Stieltjes measure.
date: 2025-09-02T09:00:00+08:00
---

**Setup.**

Let $G:\mathbb{R}\to\mathbb{R}$ be a non-decreasing and right-continuous function. The Lebesgue–Stieltjes measure $\mu_G$ on the Borel $\sigma$-algebra $\mathcal{B}(\mathbb{R})$ is defined by $\mu_G((a,b]) \coloneqq G(b)-G(a)$ for any interval $(a,b]$. For any $x \in \mathbb{R}$, we define the left-hand limit and the jump size of $G$ at $x$ as follows:

$$
G(x-) \coloneqq \sup_{t<x} G(t) = \lim_{t \uparrow x} G(t), \qquad \Delta_G(x) \coloneqq G(x) - G(x-)
$$

Since $G$ is non-decreasing, $\Delta_G(x) \ge 0$.

**Theorem (Atoms and Continuity in Lebesgue–Stieltjes Measures).**

Let $G$ and $\mu_G$ be as defined above.
1. The function $G$ is discontinuous at a point $x \in \mathbb{R}$ if and only if $\Delta_G(x) > 0$.
2. For any $x \in \mathbb{R}$, the measure of the singleton set $\{x\}$ is equal to the jump size of $G$ at $x$, i.e., $\mu_G(\{x\}) = \Delta_G(x)$.
3. The measure $\mu_G$ has no atoms (i.e., $\mu_G(\{x\}) = 0$ for all $x \in \mathbb{R}$) if and only if the function $G$ is continuous on $\mathbb{R}$.

*Proof.*

(1) Since $G$ is non-decreasing, the left-hand limit $G(x-) = \lim_{t \uparrow x} G(t)$ exists and satisfies $G(x-) \le G(x)$. By hypothesis, $G$ is right-continuous, so $\lim_{t \downarrow x} G(t) = G(x)$. A discontinuity at $x$ occurs if and only if the left and right limits are unequal, which for a right-continuous function means $G(x-) \ne G(x)$. Monotonicity implies this is equivalent to $G(x) > G(x-)$. This chain of equivalences establishes the result: $G$ is discontinuous at $x \Leftrightarrow G(x-) \ne G(x) \Leftrightarrow G(x) > G(x-) \Leftrightarrow \Delta_G(x) > 0$.

(2) For any $x \in \mathbb{R}$, the singleton set $\{x\}$ can be expressed as the intersection of a decreasing sequence of intervals: $\{x\} = \bigcap_{n=1}^\infty (x - 1/n, x]$. Since $G$ is real-valued, $\mu_G((x-1, x]) = G(x) - G(x-1)$ is finite. By the continuity from above property of measures, we have:
$$
\begin{align*}
\mu_G(\{x\}) &= \mu_G\left(\bigcap_{n=1}^\infty (x - 1/n, x]\right) \\
&= \lim_{n\to\infty} \mu_G((x - 1/n, x]) \\
&= \lim_{n\to\infty} (G(x) - G(x - 1/n)) \\
&= G(x) - \lim_{n\to\infty} G(x - 1/n) \\
&= G(x) - G(x-) = \Delta_G(x).
\end{align*}
$$

(3) The measure $\mu_G$ has no atoms if and only if $\mu_G(\{x\}) = 0$ for all $x \in \mathbb{R}$. By part (2), this is equivalent to $\Delta_G(x) = 0$ for all $x \in \mathbb{R}$. By part (1), this is equivalent to $G$ being continuous at every $x \in \mathbb{R}$.
$\square$