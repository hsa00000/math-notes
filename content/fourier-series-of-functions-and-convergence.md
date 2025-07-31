---
title: "Fourier Series of Functions: A Comprehensive Analysis of Convergence and Smoothness"
description: This note provides a complete and detailed analysis of the convergence properties and resulting smoothness of a function's Fourier series. The behavior for each classical function space (L², C⁰, C¹, C^k, C^∞) is proven by rigorously analyzing the function's Fourier coefficients and applying the convergence theorems for general trigonometric series.
---

**0. From Functions to Series: The Fundamental Definition.**

Our inquiry begins by defining a canonical map from a function to a trigonometric series. This definition is not arbitrary; it is derived by assuming a "perfect" series representation exists and then using the mathematical properties of the basis functions to uniquely determine the coefficients.

**Theorem (The Euler-Fourier Formulas).**
Let $f: \mathbb{R} \to \mathbb{C}$ be a $2\pi$-periodic function such that it is integrable on $[0, 2\pi]$ (i.e., $f \in L^1([0, 2\pi])$). The sequence of complex numbers $\{c_n[f]\}_{n \in \mathbb{Z}}$, defined by the integral
$$
c_n[f] = \frac{1}{2\pi} \int_{0}^{2\pi} f(x) e^{-inx} \,dx
$$
are the ***Fourier coefficients*** of $f$. The trigonometric series constructed with these coefficients,
$$
S[f](x) = \sum_{n=-\infty}^{\infty} c_n[f] \, e^{inx}
$$
is the ***Fourier series*** associated with the function $f$.

*Proof (A Derivation of the Formula).*
This is a definition, but it is motivated by a formal derivation. We start by positing that a function $f(x)$ can be represented by a uniformly convergent trigonometric series, which allows term-by-term operations.
$$
f(x) = \sum_{n=-\infty}^{\infty} c_n e^{i n x}
$$
To isolate a single coefficient, say $c_k$, we exploit the **orthogonality property** of the complex exponential functions. This property, fundamental to Fourier analysis, states that over an interval of length $2\pi$:
$$
\int_{0}^{2\pi} e^{imx} \overline{e^{ikx}} \,dx = \int_{0}^{2\pi} e^{i(m-k)x} \,dx = \begin{cases} 2\pi & \text{if } m = k \\ 0 & \text{if } m \ne k \end{cases}
$$
We multiply our assumed series representation by $\overline{e^{ikx}} = e^{-ikx}$:
$$
f(x) e^{-ikx} = \sum_{n=-\infty}^{\infty} c_n e^{i n x} e^{-ikx} = \sum_{n=-\infty}^{\infty} c_n e^{i(n-k)x}
$$
Integrating both sides from $0$ to $2\pi$ and leveraging the uniform convergence to swap the integral and summation yields:
$$
\int_{0}^{2\pi} f(x) e^{-ikx} \,dx = \sum_{n=-\infty}^{\infty} c_n \left( \int_{0}^{2\pi} e^{i(n-k)x} \,dx \right).
$$
Due to orthogonality, every integral on the right is zero except for the single term where $n=k$. The infinite sum thus collapses, leaving:
$$
\int_{0}^{2\pi} f(x) e^{-ikx} \,dx = c_k \cdot (2\pi).
$$
Solving for $c_k$ provides the formula in the definition. This establishes the Fourier series as the unique, natural candidate for a trigonometric series representation of a function. The critical question remains: when does this formal series converge, and what is the nature of its sum?
$\square$

**1. Convergence for L² Functions (Square-Integrable).**

The space $L^2([0, 2\pi])$ consists of functions whose squared magnitude is integrable, representing functions of finite "energy".

***A. Convergence TO the Original Function.***

**Theorem (L² and Pointwise Convergence for L² Functions).**
Let $f \in L^2([0, 2\pi])$. Then:
1.  The Fourier series $S[f]$ converges to $f$ in the $L^2$ norm.
2.  The Fourier series $S[f](x)$ converges to $f(x)$ for almost every $x \in [0, 2\pi]$.

*Proof.*
1.  **L² Convergence:** This is the **Riesz-Fischer Theorem**. It is a cornerstone of the Hilbert space theory of Fourier analysis, proving that the partial sums $S_N[f]$ form a Cauchy sequence in the complete space $L^2([0, 2\pi])$ which converges to $f$. Its proof is foundational to functional analysis and is stated here without derivation.

2.  **Pointwise Convergence:** This proof perfectly links the function space to our theorems from Lecture 1.
    *   **Analyze the Coefficients:** A direct consequence of the L² theory is **Parseval's Identity**: $\sum_{n=-\infty}^{\infty} |c_n[f]|^2 = \frac{1}{2\pi} \int_0^{2\pi} |f(x)|^2 \,dx$. Since $f \in L^2$, the integral on the right is finite by definition. Therefore, the sum of the squared magnitudes of the coefficients is finite. This proves that the sequence of Fourier coefficients $\{c_n[f]\}$ is a member of the space $\ell^2(\mathbb{Z})$.
    *   **Apply Lecture 1 Theorem:** Our "series-first" lecture presented **Carleson's Theorem**, a deep result stating that if a sequence $\{c_n\}$ is in $\ell^2$, its trigonometric series $\sum c_n e^{inx}$ converges pointwise for almost every $x$.
    *   **Conclusion:** Since the coefficients of our $L^2$ function belong to $\ell^2$, Carleson's theorem directly applies and guarantees that $S[f](x)$ converges pointwise almost everywhere to $f(x)$.
$\square$

***B. Smoothness of the Resulting Series.***

The resulting function defined by the sum of the series, $g(x) = S[f](x)$, is precisely $f(x)$ (almost everywhere). Therefore, the sum function $g$ belongs to the same space as the original function, $L^2$. There is no inherent gain in regularity.

**2. Convergence for C¹ Functions (Continuously Differentiable).**

Requiring one degree of smoothness—a continuous derivative—radically improves convergence.

***A. Convergence TO the Original Function.***

**Theorem (Absolute and Uniform Convergence for C¹ Functions).**
Let $f \in C^1([0, 2\pi])$. Its Fourier series $S[f]$ converges absolutely and uniformly to $f(x)$.

*Proof.*
The strategy is to show that the coefficients $\{c_n[f]\}$ are absolutely summable ($\in \ell^1$). We then invoke the strongest convergence theorem from Lecture 1.

1.  **Relate Coefficients of f and f':** Using integration by parts for $n \ne 0$:
    $$
    c_n[f'] = \frac{1}{2\pi} \int_0^{2\pi} f'(x) e^{-inx} dx = \frac{1}{2\pi} \left( [f(x)e^{-inx}]_0^{2\pi} + in \int_0^{2\pi} f(x) e^{-inx} dx \right).
    $$
    Periodicity of both $f(x)$ and $e^{-inx}$ makes the boundary term zero. The remaining integral is $2\pi c_n[f]$. This gives the crucial decay-rate relationship: $c_n[f] = \frac{c_n[f']}{in}$.

2.  **Establish Absolute Summability:** We must prove $\sum |c_n[f]| < \infty$.
    *   Since $f \in C^1$, its derivative $f'$ is continuous on $[0, 2\pi]$. Any continuous function on a compact interval is in $L^2$. Thus, $f' \in L^2$.
    *   This implies the coefficients of $f'$ are square-summable: $\{c_n[f']\} \in \ell^2$.
    *   To bound the sum $\sum |c_n[f]| = \sum_{n \ne 0} \frac{1}{|n|} |c_n[f']|$, we use the **Cauchy-Schwarz inequality**: $(\sum a_k b_k)^2 \le (\sum a_k^2)(\sum b_k^2)$.
        $$
        \left( \sum_{n \ne 0} \frac{1}{|n|} |c_n[f']| \right)^2 \le \left( \sum_{n \ne 0} \frac{1}{n^2} \right) \left( \sum_{n \ne 0} |c_n[f']|^2 \right).
        $$
    *   The first bracket is a convergent p-series ($=2 \cdot \pi^2/6$). The second bracket converges because $\{c_n[f']\} \in \ell^2$. The product is finite, proving that $\sum |c_n[f]|$ is finite. Thus, $\{c_n[f]\} \in \ell^1$.

3.  **Apply Lecture 1 Theorem:** From Lecture 1, the **Weierstrass M-Test** proves that if a coefficient sequence $\{c_n\}$ is in $\ell^1$, the series $\sum c_n e^{inx}$ converges absolutely and uniformly.

4.  **Conclusion:** The Fourier series $S[f]$ converges absolutely and uniformly. Since $f$ is continuous and the convergence is uniform, the limit of the series must be $f(x)$.
$\square$

***B. Smoothness of the Resulting Series.***

Since we proved that $S[f]$ converges uniformly to $f$, and $f$ is a $C^1$ function, the resulting sum function is itself in $C^1$.

**3. The Hierarchy of Smoothness: C^k and C^∞ Functions.**

**Theorem (Rapid Convergence for C^k Functions).**
Let $f \in C^k([0, 2\pi])$ for $k \ge 1$. Its Fourier series $S[f]$ converges absolutely and uniformly to $f$, and the coefficients exhibit rapid polynomial decay: $|c_n[f]| = O(|n|^{-k})$.

*Proof.*
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

***B. Smoothness of the Resulting Series.***
The sum function is $f$, which belongs to $C^k$.

**Theorem (Super-Rapid Convergence for C^∞ / Schwartz Functions).**
Let $f$ be a $C^\infty$ function on $[0, 2\pi]$. The sequence of its Fourier coefficients $\{c_n[f]\}$ is rapidly decreasing (of Schwartz class). The Fourier series $S[f]$ converges to $f$ absolutely and uniformly, and the resulting sum function is itself $C^\infty$.

*Note on Terminology:* For functions on the real line $\mathbb{R}$, a Schwartz function must be $C^\infty$ *and* all its derivatives must decay rapidly at infinity. For periodic functions on a compact interval like $[0, 2\pi]$, the decay conditions at infinity are moot. A function is a Schwartz function on the circle if and only if it is $C^\infty$.

*Proof.*
1.  **Analyze the Coefficients:** The formula $c_n[f] = \frac{c_n[f^{(k)}]}{(in)^k}$ is valid for **every** integer $k \ge 1$. Since $c_n[f^{(k)}]$ is bounded for each $k$, this means $|c_n[f]|$ decays faster than any inverse polynomial power, $|c_n[f]|=O(n^{-k})$ for all $k$. This is the definition of a rapidly decreasing (Schwartz class) sequence. This guarantees $\{c_n[f]\} \in \ell^1$, so $S[f]$ converges absolutely and uniformly to $f$.

2.  **Smoothness of the Resulting Sum Function:** We must show that the function $g(x) = S[f](x)$ is infinitely differentiable. We use the **Moment Conditions Theorem** from Lecture 1, which states that a series sum is in $C^j$ if $\sum |n|^j |c_n| < \infty$.
    *   Let's check the condition for the $j$-th derivative of $S[f]$. We need to sum $\sum_n |n|^j |c_n[f]|$.
    *   Since $\{c_n[f]\}$ is rapidly decreasing, we can use the decay property for an order higher than required, for example, for $k=j+2$: we know $|c_n[f]| \le M/|n|^{j+2}$ for some constant $M$.
    *   Substituting this in, we get:
        $$
        \sum_{n \ne 0} |n|^j |c_n[f]| \le \sum_{n \ne 0} |n|^j \frac{M}{|n|^{j+2}} = M \sum_{n \ne 0} \frac{1}{n^2} < \infty.
        $$
    *   This demonstrates that the series for the $j$-th derivative converges absolutely and uniformly. Since this argument holds true for **any** choice of $j$, the sum function $g(x) = f(x)$ must be in $C^j$ for all $j$, which means it is a $C^\infty$ function.
$\square$

**4. Comprehensive Summary of Convergence**

This table details both the convergence of the series *to* the original function and the intrinsic smoothness class of the function defined by the series sum itself.

| Function Space of `f`            | L² Conv. to `f` | Pointwise Conv. to `f` | Uniform Conv. to `f` | Absolute Conv. | Smoothness Class of the Sum Function `S[f]` |
| -------------------------------- | :---------------: | :-----------------------: | :--------------------: | :------------------: | :-------------------------------------------: |
| **L²** (Square-Integrable)       |      **Yes**      |      Almost Everywhere      |     Not Guaranteed     | Not Guaranteed |                   $L^2$                       |
| **C⁰** (Continuous)              |      **Yes**      |      Not Guaranteed       |     Not Guaranteed     | Not Guaranteed |                   Not Guaranteed                       |
| **C¹** (Continuously Diff.)      |      **Yes**      |          **Yes**          |       **Yes**       |      **Yes**      |                   $C^1$                       |
| **C^k** (k ≥ 2 times Diff.)      |      **Yes**      |          **Yes**          |       **Yes**       |      **Yes**      |                   $C^k$                       |
| **C^∞** (Smooth) / Schwartz      |      **Yes**      |          **Yes**          |       **Yes**       |      **Yes**      |                  $C^\infty$                   |