---
title: Convergence of General Trigonometric Series
description: This note provides a self-contained, detailed exploration of the conditions on a sequence of coefficients that determine the convergence properties of its associated trigonometric series. The theorems are presented with complete, rigorous proofs intended for a reader with a background in elementary real analysis.
---

**0. Preliminaries.**

**Definition.**
A ***general trigonometric series*** is a formal mathematical expression written as
$$
f(x) \sim \sum_{n=-\infty}^{\infty} c_n e^{i n x}
$$
where $\{c_n\}_{n \in \mathbb{Z}}$ is a sequence of complex numbers, called the coefficients, and $x$ is a real variable. The symbol `~` is used to denote that this is a formal series, and we make no initial assumptions about its convergence or its relationship to any function $f$.

**Definition.**
The ***N-th symmetric partial sum*** of the series is the function $S_N: \mathbb{R} \to \mathbb{C}$ defined by the finite sum
$$
S_N(x) = \sum_{k=-N}^{N} c_k e^{i k x}.
$$
The series is said to converge pointwise at a specific value $x$ if the sequence of complex numbers $\{S_N(x)\}_{N \ge 0}$ has a well-defined limit as $N \to \infty$.

**1. Necessary Conditions and Divergence.**

Before establishing conditions that guarantee convergence, we identify the most basic prerequisite. A series cannot converge if its individual terms do not shrink to nothing.

**Theorem.**
If the series $\sum c_n e^{i n x}$ converges at a point $x$, then the terms corresponding to indices $N$ and $-N$ must jointly vanish as $N \to \infty$. Specifically,
$$
\lim_{N \to \infty} \left( c_N e^{iNx} + c_{-N} e^{-iNx} \right) = 0.
$$

*Proof.*
Let $\{S_N(x)\}$ be the sequence of partial sums. The hypothesis that the series converges at $x$ means that $\lim_{N \to \infty} S_N(x) = L$ for some finite complex number $L$.

1.  A convergent sequence is necessarily a Cauchy sequence. This implies that the difference between successive terms of the sequence must approach zero.
    $$
    \lim_{N \to \infty} \left( S_N(x) - S_{N-1}(x) \right) = L - L = 0.
    $$

2.  We compute this difference explicitly from the definition of the partial sum:
    $$
    S_N(x) - S_{N-1}(x) = \left( \sum_{k=-N}^{N} c_k e^{ikx} \right) - \left( \sum_{k=-(N-1)}^{N-1} c_k e^{ikx} \right).
    $$
    All terms except those with index $N$ and $-N$ cancel, leaving
    $$
    S_N(x) - S_{N-1}(x) = c_N e^{iNx} + c_{-N} e^{-iNx}.
    $$

3.  Combining these two points yields the stated result.
$\square$

**Theorem (Kolmogorov).**
The condition $\lim_{|n| \to \infty} c_n = 0$ is necessary for convergence on a set of positive measure, but it is not sufficient for pointwise convergence anywhere. There exists a sequence $\{c_n\}$ with $c_n \to 0$ for which the series $\sum c_n e^{i n x}$ diverges for every $x \in \mathbb{R}$.

*Proof.*
The proof is a landmark result in harmonic analysis that involves the intricate construction of an $L^1$ function whose Fourier series diverges everywhere. This construction is highly advanced and is omitted. The significance of this theorem is profound: it demonstrates that there is no simple condition on the magnitude of the coefficients alone that can guarantee pointwise convergence for a general series.
$\square$

**2. Absolute and Uniform Convergence.**

The strongest and most straightforward type of convergence occurs when the coefficients themselves are absolutely summable. This guarantees excellent behavior for the series.

**Theorem (Weierstrass M-Test for Trigonometric Series).**
If the sequence of coefficients is absolutely summable, meaning $\sum_{n=-\infty}^{\infty} |c_n| < \infty$, then the series converges absolutely and uniformly on $\mathbb{R}$ to a function $f(x)$ which is continuous.

*Proof.*
The goal is to show that the sequence of functions $\{S_N(x)\}$ converges uniformly. We work within the space of bounded, continuous functions on $\mathbb{R}$, denoted $C_b(\mathbb{R})$, which is a complete metric space (a Banach space) under the supremum norm, $||g||_\infty = \sup_{x \in \mathbb{R}} |g(x)|$.

1.  **Cauchy Sequence Argument:** We show that $\{S_N\}$ is a Cauchy sequence in this space. Let $M > N \ge 0$. Consider the norm of the difference:
    $$
    ||S_M - S_N||_\infty = \sup_{x \in \mathbb{R}} \left| \sum_{|k|=N+1}^{M} c_k e^{ikx} \right|.
    $$

2.  **Applying the Triangle Inequality:** By the triangle inequality and the fact that $|e^{ikx}|=1$:
    $$
    \sup_{x \in \mathbb{R}} \left| \sum_{|k|=N+1}^{M} c_k e^{ikx} \right| \le \sum_{|k|=N+1}^{M} |c_k| |e^{ikx}| = \sum_{|k|=N+1}^{M} |c_k|.
    $$

3.  **Using the Hypothesis:** The hypothesis is that the series of real numbers $\sum |c_n|$ converges. A convergent series must have a Cauchy sequence of partial sums. This means that for any $\epsilon > 0$, there exists an integer $N_0$ such that for all $M > N > N_0$, the tail sum is small: $\sum_{|k|=N+1}^{M} |c_k| < \epsilon$.

4.  **Conclusion:** Combining these steps, for $M > N > N_0$, we have $||S_M - S_N||_\infty < \epsilon$. Thus, $\{S_N\}$ is a Cauchy sequence in the Banach space $C_b(\mathbb{R})$. Because the space is complete, the sequence must converge to a limit function $f \in C_b(\mathbb{R})$. The uniform limit of a sequence of continuous functions (each $S_N$ is a finite sum of continuous functions, hence continuous) is itself continuous.
$\square$

**Theorem (Moment Conditions for Smoothness).**
Let $k \ge 1$ be an integer. If the "k-th moment" of the coefficients is finite, i.e., $\sum_{n=-\infty}^{\infty} |n|^k |c_n| < \infty$, then the series converges uniformly to a function $f \in C^k(\mathbb{R})$ (meaning $f$ has $k$ continuous derivatives). Furthermore, these derivatives can be computed by term-by-term differentiation of the series.

*Proof.*
We proceed by induction on $k$.

1.  **Base Case (k=1):** We are given $\sum |n||c_n| < \infty$. Since $|c_n| \le |n||c_n|$ for $|n| \ge 1$, the condition $\sum|c_n| < \infty$ also holds. By the previous theorem, the series for $f(x)$ converges uniformly to a continuous function $f$.
    Now consider the formal series of derivatives:
    $$
    g(x) \sim \sum_{n=-\infty}^{\infty} (in) c_n e^{inx}.
    $$
    Let $g_N(x) = S_N'(x)$ be its partial sums. The sum of the absolute values of the coefficients of this new series is $\sum |in c_n| = \sum |n||c_n|$. By hypothesis, this sum is finite. Applying the Weierstrass M-Test to this new series, we conclude that the functions $\{g_N(x)\}$ converge uniformly to a continuous function $g(x)$.
    A fundamental theorem of analysis states that if $\{S_N\}$ converges to $f$ (even just pointwise) and the sequence of derivatives $\{S_N'\}$ converges *uniformly* to $g$, then $f$ must be differentiable and $f' = g$. Since $g$ is continuous, $f \in C^1(\mathbb{R})$.

2.  **Inductive Step:** Assume the theorem holds for $k-1$. Suppose $\sum |n|^k |c_n| < \infty$. Let $g(x) = \sum (in) c_n e^{inx}$. The coefficients of this series are $d_n = in c_n$. We check the $(k-1)$-th moment condition for this new series:
    $$
    \sum |n|^{k-1} |d_n| = \sum |n|^{k-1} |in c_n| = \sum |n|^k |c_n|.
    $$
    This is finite by our hypothesis. By the inductive hypothesis, the series for $g(x)$ converges to a function $g \in C^{k-1}(\mathbb{R})$. Since $f' = g$, it follows that $f \in C^k(\mathbb{R})$. The proof is complete by induction.
$\square$

**3. Conditional and Pointwise Convergence.**

When absolute convergence fails, the series can still converge if the coefficients decay in a sufficiently structured manner. The key tool here is summation by parts.

**Definition.**
A sequence of complex numbers $\{c_n\}_{n \in \mathbb{Z}}$ is of ***bounded variation*** if the sum of the magnitudes of its successive differences is finite: $\sum_{n=-\infty}^{\infty} |c_n - c_{n+1}| < \infty$.

**Theorem (Jordan-Dirichlet Test).**
If the sequence of coefficients $\{c_n\}$ is of bounded variation and $\lim_{|n| \to \infty} c_n = 0$, then the series converges pointwise for every $x$ which is not an integer multiple of $2\pi$.

*Proof.*
It suffices to prove the convergence of the sum over positive indices, $\sum_{n=1}^\infty c_n e^{inx}$, as the argument for negative indices is identical.

1.  **Summation by Parts (Abel's Transformation):** Let $D_k(x) = \sum_{j=1}^k e^{ijx}$. The formula for summation by parts states:
    $$
    \sum_{n=1}^N c_n e^{inx} = c_N D_N(x) - \sum_{n=1}^{N-1} (c_{n+1}-c_n)D_n(x).
    $$

2.  **Boundedness of the Dirichlet Sums:** The sum $D_k(x)$ is a finite geometric series. For $x \notin 2\pi\mathbb{Z}$, $e^{ix} \ne 1$.
    $$
    |D_k(x)| = \left| e^{ix} \frac{1-e^{ikx}}{1-e^{ix}} \right| = \frac{|1-e^{ikx}|}{|1-e^{ix}|} \le \frac{2}{|1-e^{ix}|} = \frac{1}{|\sin(x/2)|}.
    $$
    Let $M_x = 1/|\sin(x/2)|$. This bound $M_x$ is finite for our chosen $x$ and is independent of $k$.

3.  **Analyzing the Limit:** We take the limit of the summation-by-parts formula as $N \to \infty$.
    *   **First Term:** $|c_N D_N(x)| \le |c_N| M_x$. Since $c_N \to 0$ by hypothesis, this term vanishes: $\lim_{N \to \infty} c_N D_N(x) = 0$.
    *   **Second Term:** We examine the infinite series $\sum_{n=1}^{\infty} (c_{n+1}-c_n)D_n(x)$. We show it converges absolutely:
        $$
        \sum_{n=1}^{\infty} |(c_{n+1}-c_n)D_n(x)| \le \sum_{n=1}^{\infty} |c_{n+1}-c_n| |D_n(x)| \le M_x \sum_{n=1}^{\infty} |c_{n+1}-c_n|.
        $$
        This final sum is finite by the hypothesis that $\{c_n\}$ is of bounded variation. Since the series of absolute values converges, the series itself converges.

4.  **Conclusion:** Both terms on the right-hand side of the summation-by-parts formula have a well-defined limit. Therefore, the left-hand side must also converge.
$\square$

**4. L² and Almost Everywhere Convergence.**

A paradigm shift in modern analysis was to consider convergence not at every point, but in an average sense, which requires tools from Hilbert space theory.

**Theorem (Riesz-Fischer).**
Let the coefficients be square-summable, i.e., $\{c_n\} \in \ell^2(\mathbb{Z})$, meaning $\sum_{n=-\infty}^{\infty} |c_n|^2 < \infty$. Then there exists a unique function $f \in L^2([0, 2\pi])$ such that the partial sums $S_N$ converge to $f$ in the $L^2$ norm.

*Proof.*
The space $L^2([0, 2\pi])$ of square-integrable functions is a complete Hilbert space. The proof shows that $\{S_N\}$ is a Cauchy sequence in this space.

1.  **Orthogonality:** The basis functions $\{e^{inx}\}_{n\in\mathbb{Z}}$ are orthogonal over $[0, 2\pi]$, satisfying $\int_0^{2\pi} e^{ijx} \overline{e^{ikx}} dx = 2\pi \delta_{jk}$.

2.  **Computing the Norm of the Difference:** For $M > N$, we compute the squared $L^2$-norm of the difference of partial sums:
    $$
    \begin{align*}
    ||S_M - S_N||_{L^2}^2 &= \int_0^{2\pi} \left| \sum_{|k|=N+1}^M c_k e^{ikx} \right|^2 dx \\
    &= \int_0^{2\pi} \left( \sum_{|j|=N+1}^M c_j e^{ijx} \right) \left( \sum_{|k|=N+1}^M \overline{c_k} e^{-ikx} \right) dx \\
    &= \sum_{|j|=N+1}^M \sum_{|k|=N+1}^M c_j \overline{c_k} \int_0^{2\pi} e^{i(j-k)x} dx.
    \end{align*}
    $$
    Due to orthogonality, the integral is zero unless $j=k$, in which case it is $2\pi$.

3.  **Result:** The expression simplifies to:
    $$
    ||S_M - S_N||_{L^2}^2 = 2\pi \sum_{|k|=N+1}^M |c_k|^2.
    $$

4.  **Conclusion:** The hypothesis $\sum |c_n|^2 < \infty$ means that the tail of this real series must go to zero. Thus, for any $\epsilon > 0$, we can find $N_0$ so that for $M > N > N_0$, $||S_M - S_N||_{L^2}^2 < \epsilon$. This shows $\{S_N\}$ is a Cauchy sequence in $L^2$. By the completeness of the space, a limit function $f \in L^2$ must exist.
$\square$

**Theorem (Carleson-Hunt).**
If $\{c_n\} \in \ell^2(\mathbb{Z})$, then the partial sums $S_N(x)$ converge pointwise to the limit function $f(x)$ for almost every $x \in [0, 2\pi]$.

*Proof.*
The proof of this theorem, which settled a 50-year-old conjecture by Lusin, is one of the most complex and profound achievements in 20th-century mathematical analysis. It is far beyond the scope of this summary and is omitted. Its statement, however, is a beautiful bridge between the worlds of average ($L^2$) convergence and pointwise convergence.
$\square$