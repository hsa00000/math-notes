---
title: "Fourier Series of Functions: A Comprehensive Analysis of Convergence and Smoothness"
description: This note provides a complete and detailed analysis of the convergence properties and resulting smoothness of a function's Fourier series. The behavior for each classical function space ($L^2$, C⁰, C¹, C^k, C^∞) is proven by rigorously analyzing the function's Fourier coefficients and applying the convergence theorems for general trigonometric series.
date: 2025-07-31
---

**0. From Functions to Series: The Fundamental Definition.**

Our inquiry begins by defining a canonical map from a function to a trigonometric series. This definition is not arbitrary; it is derived by assuming a "perfect" series representation exists and then using the mathematical properties of the basis functions to uniquely determine the coefficients.

**Theorem (Uniqueness of Coefficients for Uniformly Convergent Series).**

Let $f: \mathbb{R} \to \mathbb{C}$ be a $2\pi$-periodic function. If $f(x)$ is the sum of a uniformly convergent trigonometric series

$$
f(x) = \sum_{n=-\infty}^{\infty} c_n e^{inx}
$$

then the coefficients $c_n$ are uniquely determined for each $n \in \mathbb{Z}$ by the formula

$$
c_n = \frac{1}{2\pi} \int_{0}^{2\pi} f(x) e^{-inx} dx
$$

_Proof._
The basis functions $\{e^{inx}\}_{n \in \mathbb{Z}}$ are orthogonal on the interval $[0, 2\pi]$. For any integers $n, k$, this property is expressed as:

$$
\int_{0}^{2\pi} e^{inx} e^{-ikx} dx = \int_{0}^{2\pi} e^{i(n-k)x} dx = 2\pi \delta_{nk}
$$

where $\delta_{nk}$ is the Kronecker delta. To find the coefficient $c_k$ for a fixed integer $k$, multiply the series representation of $f(x)$ by $e^{-ikx}$ and integrate over $[0, 2\pi]$. The uniform convergence of the series permits the interchange of summation and integration.

$$
\begin{align*}
\int_{0}^{2\pi} f(x) e^{-ikx} dx &= \int_{0}^{2\pi} \left( \sum_{n=-\infty}^{\infty} c_n e^{inx} \right) e^{-ikx} dx \\
&= \sum_{n=-\infty}^{\infty} c_n \left( \int_{0}^{2\pi} e^{inx} e^{-ikx} dx \right) \\
&= \sum_{n=-\infty}^{\infty} c_n (2\pi \delta_{nk}) \\
&= c_k \cdot 2\pi
\end{align*}
$$

Solving for $c_k$ yields the stated formula.
$\square$

**Definition (Fourier Coefficients and Fourier Series).**

Let $f: \mathbb{R} \to \mathbb{C}$ be a $2\pi$-periodic function that is integrable on $[0, 2\pi]$, i.e., $f \in L^1([0, 2\pi])$. The **_Fourier coefficients_** of $f$ are the sequence of complex numbers $\{c_n[f]\}_{n \in \mathbb{Z}}$ defined by

$$
c_n[f] = \frac{1}{2\pi} \int_{0}^{2\pi} f(x) e^{-inx} dx
$$

The **_Fourier series_** of $f$, denoted $S[f](x)$, is the trigonometric series constructed with these coefficients:

$$
S[f](x) = \sum_{n=-\infty}^{\infty} c_n[f] e^{inx}
$$

**1. Convergence for $L^2$ Functions (Square-Integrable).**

The space $L^2([0, 2\pi])$ consists of functions whose squared magnitude is integrable, representing functions of finite "energy".

**_A. Convergence TO the Original Function._**

**Theorem ($L^2$ and Pointwise Convergence for $L^2$ Functions).**
Let $f \in L^2([0, 2\pi])$. Then:

1.  The Fourier series $S[f]$ converges to $f$ in the $L^2$ norm.
2.  The Fourier series $S[f](x)$ converges to $f(x)$ for almost every $x \in [0, 2\pi]$.

_Proof._

1.  **$L^2$ Convergence:** This is the **Riesz-Fischer Theorem**. It is a cornerstone of the Hilbert space theory of Fourier analysis, proving that the partial sums $S_N[f]$ form a Cauchy sequence in the complete space $L^2([0, 2\pi])$ which converges to $f$. Its proof is foundational to functional analysis and is stated here without derivation.

2.  **Pointwise Convergence:** This proof perfectly links the function space to our theorems from Lecture 1.
    _ **Analyze the Coefficients:** A direct consequence of the $L^2$ theory is **Parseval's Identity**: $\sum_{n=-\infty}^{\infty} |c_n[f]|^2 = \frac{1}{2\pi} \int_0^{2\pi} |f(x)|^2 \,dx$. Since $f \in L^2$, the integral on the right is finite by definition. Therefore, the sum of the squared magnitudes of the coefficients is finite. This proves that the sequence of Fourier coefficients $\{c_n[f]\}$ is a member of the space $\ell^2(\mathbb{Z})$.
    - **Apply Lecture 1 Theorem:** Our "series-first" lecture presented **Carleson's Theorem**, a deep result stating that if a sequence $\{c_n\}$ is in $\ell^2$, its trigonometric series $\sum c_n e^{inx}$ converges pointwise for almost every $x$. \* **Conclusion:** Since the coefficients of our $L^2$ function belong to $\ell^2$, Carleson's theorem directly applies and guarantees that $S[f](x)$ converges pointwise almost everywhere to $f(x)$.
      $\square$

**_B. Smoothness of the Resulting Series._**

The resulting function defined by the sum of the series, $g(x) = S[f](x)$, is precisely $f(x)$ (almost everywhere). Therefore, the sum function $g$ belongs to the same space as the original function, $L^2$. There is no inherent gain in regularity.

**2. Convergence for C¹ Functions (Continuously Differentiable).**

Requiring one degree of smoothness—a continuous derivative—radically improves convergence.

**_A. Convergence TO the Original Function._**

**Theorem (Absolute and Uniform Convergence for C¹ Functions).**
Let $f \in C^1([0, 2\pi])$. Its Fourier series $S[f]$ converges absolutely and uniformly to $f(x)$.

_Proof._
The strategy is to show that the coefficients $\{c_n[f]\}$ are absolutely summable ($\in \ell^1$). We then invoke the strongest convergence theorem from Lecture 1.

1.  **Relate Coefficients of f and f':** Using integration by parts for $n \ne 0$:

    $$
    c_n[f'] = \frac{1}{2\pi} \int_0^{2\pi} f'(x) e^{-inx} dx = \frac{1}{2\pi} \left( [f(x)e^{-inx}]_0^{2\pi} + in \int_0^{2\pi} f(x) e^{-inx} dx \right).
    $$

    Periodicity of both $f(x)$ and $e^{-inx}$ makes the boundary term zero. The remaining integral is $2\pi c_n[f]$. This gives the crucial decay-rate relationship: $c_n[f] = \frac{c_n[f']}{in}$.

2.  **Establish Absolute Summability:** We must prove $\sum |c_n[f]| < \infty$.

    - Since $f \in C^1$, its derivative $f'$ is continuous on $[0, 2\pi]$. Any continuous function on a compact interval is in $L^2$. Thus, $f' \in L^2$.
    - This implies the coefficients of $f'$ are square-summable: $\{c_n[f']\} \in \ell^2$.
    - To bound the sum $\sum |c_n[f]| = \sum_{n \ne 0} \frac{1}{|n|} |c_n[f']|$, we use the **Cauchy-Schwarz inequality**: $(\sum a_k b_k)^2 \le (\sum a_k^2)(\sum b_k^2)$.
      $$
      \left( \sum_{n \ne 0} \frac{1}{|n|} |c_n[f']| \right)^2 \le \left( \sum_{n \ne 0} \frac{1}{n^2} \right) \left( \sum_{n \ne 0} |c_n[f']|^2 \right).
      $$
    - The first bracket is a convergent p-series ($=2 \cdot \pi^2/6$). The second bracket converges because $\{c_n[f']\} \in \ell^2$. The product is finite, proving that $\sum |c_n[f]|$ is finite. Thus, $\{c_n[f]\} \in \ell^1$.

3.  **Apply Lecture 1 Theorem:** From Lecture 1, the **Weierstrass M-Test** proves that if a coefficient sequence $\{c_n\}$ is in $\ell^1$, the series $\sum c_n e^{inx}$ converges absolutely and uniformly.

4.  **Conclusion:** The Fourier series $S[f]$ converges absolutely and uniformly. Since $f$ is continuous and the convergence is uniform, the limit of the series must be $f(x)$.
    $\square$

**_B. Smoothness of the Resulting Series._**

Since we proved that $S[f]$ converges uniformly to $f$, and $f$ is a $C^1$ function, the resulting sum function is itself in $C^1$.

**3. The Hierarchy of Smoothness: $C^k$ and $C^∞$ Functions.**

**Theorem (Rapid Convergence for $C^k$ Functions).**
Let $f \in C^k([0, 2\pi])$ for $k \ge 1$. Its Fourier series $S[f]$ converges absolutely and uniformly to $f$, and the coefficients exhibit rapid polynomial decay: $|c_n[f]| = O(|n|^{-k})$.

_Proof._

1.  **Analyze the Coefficients:** Iterating the differentiation rule $c_n[g'] = in \cdot c_n[g]$ for $k$ times yields:

    $$
    c_n[f] = \frac{c_n[f^{(k)}]}{(in)^k}, \quad n \ne 0.
    $$

2.  **Establish Decay Rate:** The derivative $f^{(k)}$ is continuous by hypothesis, hence its Fourier coefficients $\{c_n[f^{(k)}]\}$ are bounded by some constant $M$. This gives a precise bound on the decay of the original coefficients:

    $$
    |c_n[f]| = \frac{|c_n[f^{(k)}]}{|n|^k} \le \frac{M}{|n|^k}.
    $$

3.  **Show Absolute Summability:** The sum $\sum |c_n[f]| \le \sum M/|n|^k$. For any $k \ge 2$, this p-series converges rapidly. (The case $k=1$ was handled above). Therefore, for any $f \in C^k$ with $k \ge 1$, its coefficients are in $\ell^1$.

4.  **Apply Lecture 1 Theorem:** The Weierstrass M-Test again implies absolute and uniform convergence of $S[f]$ to $f$.
    $\square$

**_B. Smoothness of the Resulting Series._**
The sum function is $f$, which belongs to $C^k$.

**4. Comprehensive Summary of Convergence**

This table details both the convergence of the series _to_ the original function and the intrinsic smoothness class of the function defined by the series sum itself.

| Function Space of $f$           | $L^2$ Conv. to $f$ | Pointwise Conv. to $f$ | Uniform Conv. to $f$ | Absolute Conv. | Smoothness Class of the Sum Function $S[f]$ |
| ------------------------------- | :----------------: | :--------------------: | :------------------: | :------------: | :-----------------------------------------: |
| **$L^2$** (Square-Integrable)   |      **Yes**       |   Almost Everywhere    |    Not Guaranteed    | Not Guaranteed |                    $L^2$                    |
| **$C^0$** (Continuous)          |      **Yes**       |     Not Guaranteed     |    Not Guaranteed    | Not Guaranteed |               Not Guaranteed                |
| **$C^1$** (Continuously Diff.)  |      **Yes**       |        **Yes**         |       **Yes**        |    **Yes**     |                    $C^1$                    |
| **$C^k$** ($k ≥ 2$ times Diff.) |      **Yes**       |        **Yes**         |       **Yes**        |    **Yes**     |                    $C^k$                    |
| **$C^\infty$** (Smooth)         |      **Yes**       |        **Yes**         |       **Yes**        |    **Yes**     |                 $C^\infty$                  |
