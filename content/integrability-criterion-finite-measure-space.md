---
title: Integrability on Finite Measure Spaces via Tail Integral
description: A proof establishing the equivalence between the integrability of a function and the vanishing limit of its tail integral on a finite measure space.
---

**Theorem 1 (Integrability via Tail Integral on Finite Measure Spaces).**

Let $(X, \mathcal{M}, \mu)$ be a finite measure space, meaning $\mu(X) < \infty$. A measurable function $f: X \to \overline{\mathbb{R}}$ or $f: X \to \mathbb{C}$ is integrable if and only if $\lim_{t \to \infty} \int_{\{|f| \geq t\}} |f| \, d\mu = 0$.

*Proof.*
(⇒) Assume $f$ is integrable, which means $\int_X |f| \, d\mu < \infty$. Let $g_t(x) = |f(x)| \chi_{\{|f| \ge t\}}(x)$, where $\chi$ is the characteristic function. For each $x \in X$ such that $|f(x)| < \infty$, $\lim_{t \to \infty} g_t(x) = 0$. Since $f$ is integrable, $|f(x)| < \infty$ for almost every $x$. Thus, $g_t \to 0$ almost everywhere. The function $|f|$ is integrable, and $|g_t(x)| \le |f(x)|$ for all $t > 0$ and $x \in X$. By the Dominated Convergence Theorem:

$$
\lim_{t \to \infty} \int_{\{|f| \geq t\}} |f| \, d\mu = \lim_{t \to \infty} \int_X g_t \, d\mu = \int_X \lim_{t \to \infty} g_t \, d\mu = \int_X 0 \, d\mu = 0.
$$

(⇐) Assume $\lim_{t \to \infty} \int_{\{|f| \geq t\}} |f| \, d\mu = 0$. To show $f$ is integrable, we must show $\int_X |f| \, d\mu < \infty$. For any constant $M > 0$, the integral is decomposed as:

$$
\int_X |f| \, d\mu = \int_{\{|f| < M\}} |f| \, d\mu + \int_{\{|f| \geq M\}} |f| \, d\mu.
$$

The first term on the right is bounded:

$$
\int_{\{|f| < M\}} |f| \, d\mu \leq \int_{\{|f| < M\}} M \, d\mu = M \mu(\{|f| < M\}).
$$

Since $\mu(X) < \infty$, we have $\mu(\{|f| < M\}) \le \mu(X) < \infty$. Thus, $\int_{\{|f| < M\}} |f| \, d\mu$ is finite. The second term, $\int_{\{|f| \geq M\}} |f| \, d\mu$, approaches $0$ as $M \to \infty$ by hypothesis, and so is finite for any sufficiently large $M$. The integral $\int_X |f| \, d\mu$ is the sum of two finite quantities, hence it is finite.
$\square$