---
title: Fourier Series Convergence for Piecewise Smooth Functions
description: This note establishes the convergence criteria for Fourier series of piecewise smooth functions, with a specific focus on the behavior at points of continuity and at jump discontinuities.
---

**0. Preliminaries: A Broader Class of Functions.**

To analyze functions with jump discontinuities, a class of functions less restrictive than $C^1$ is required.

**Definition 1 (Piecewise Continuity).**
A function $f$ is **_piecewise continuous_** on a finite interval $[a, b]$ if it is continuous at every point in $[a, b]$ except for a finite number of points $x_i$, at each of which the left-hand and right-hand limits, denoted $f(x_i^-) = \lim_{t \to x_i^-} f(t)$ and $f(x_i^+) = \lim_{t \to x_i^+} f(t)$, exist and are finite.

**Definition 2 (Piecewise Smoothness).**
A function $f$ is **_piecewise smooth_** on an interval if both the function $f$ and its derivative $f'$ are piecewise continuous on that interval. A periodic function is piecewise smooth if it is piecewise smooth on any finite interval of one period.

**1. Pointwise Convergence Theorem for Piecewise Smooth Functions.**

The following theorem provides a definitive statement on the pointwise convergence behavior of a Fourier series for a function that is well-behaved between a finite number of jump discontinuities.

**Theorem 1 (Dirichlet's Convergence Theorem).**
Let $f: \mathbb{R} \to \mathbb{C}$ be a $2\pi$-periodic and piecewise smooth function. The Fourier series of $f$, denoted $S[f](x)$, converges for all $x \in \mathbb{R}$. The limit of the series is as follows:

1. At any point $x$ where $f$ is continuous, the series converges to the value of the function: $S[f](x) = f(x)$.
2. At any point of discontinuity $x_0$, the series converges to the arithmetic mean of the left-hand and right-hand limits:

$$
S[f](x_0) = \frac{f(x_0^+) + f(x_0^-)}{2}
$$

_Proof._
The $N$-th symmetric partial sum of the Fourier series, $S_N[f](x)$, can be expressed as a convolution integral with the Dirichlet kernel, $D_N(t) = \sum_{k=-N}^{N} e^{ikt}$.

$$
S_N[f](x) = \frac{1}{2\pi} \int_{-\pi}^{\pi} f(x-t) D_N(t) \,dt
$$

The Dirichlet kernel has the closed-form expression $D_N(t) = \frac{\sin((N + 1/2)t)}{\sin(t/2)}$ and satisfies $\frac{1}{2\pi} \int_{-\pi}^{\pi} D_N(t) \,dt = 1$. Let $L(x)$ denote the asserted limit of the series. At a point of continuity, $L(x)=f(x)$. At a discontinuity $x_0$, $L(x_0) = (f(x_0^+) + f(x_0^-))/2$.

We analyze the difference $S_N[f](x) - L(x)$. Using the integral property of $D_N(t)$, we can write:

$$
S_N[f](x) - L(x) = \frac{1}{2\pi} \int_{-\pi}^{\pi} (f(x-t) - L(x)) D_N(t) \,dt
$$

Substituting the closed form for $D_N(t)$:

$$
S_N[f](x) - L(x) = \frac{1}{2\pi} \int_{-\pi}^{\pi} \frac{f(x-t) - L(x)}{\sin(t/2)} \sin\left(\left(N + \frac{1}{2}\right)t\right) \,dt
$$

Let the function $g(t)$ be defined as $g(t) = \frac{f(x-t) - L(x)}{\sin(t/2)}$. The core of the proof is to show that $g(t)$ is an integrable function on $[-\pi, \pi]$. The only point of concern is the behavior as $t \to 0$.

As $t \to 0^+$, $x-t \to x^-$. The limit of the numerator is $f(x^-) - L(x)$.
As $t \to 0^-$, $x-t \to x^+$. The limit of the numerator is $f(x^+) - L(x)$.
In either case of continuity or discontinuity, the definition of $L(x)$ and the piecewise smoothness of $f$ (which guarantees the existence of one-sided derivatives) ensures that the limit of $g(t)$ as $t \to 0$ is finite. Specifically, by using the approximation $\sin(t/2) \approx t/2$ and applying L'Hôpital's rule, the limit is shown to depend on the one-sided derivatives of $f$ at $x$.

Since $g(t)$ is integrable, the Riemann-Lebesgue Lemma applies. The lemma states that for any $g \in L^1([-\pi, \pi])$, $\lim_{\lambda \to \infty} \int_{-\pi}^{\pi} g(t) \sin(\lambda t) \,dt = 0$. In our case, $\lambda = N + 1/2$.

Therefore, as $N \to \infty$, the integral vanishes.

$$
\lim_{N \to \infty} (S_N[f](x) - L(x)) = 0
$$

This establishes that the Fourier series converges to the stated value $L(x)$. $\square$

**Example: The Sawtooth Wave.**

**Definition.**
Consider the function $f(x)=x$ on the interval $[0, 2\pi)$, extended periodically to all of $\mathbb{R}$. This function has jump discontinuities at every $x = 2k\pi$ for $k \in \mathbb{Z}$.

_Proof._
We compute the Fourier coefficients of $f(x)=x$ on $[0, 2\pi)$.
The zeroth coefficient is

$$
c_0[f] = \frac{1}{2\pi} \int_0^{2\pi} x \, dx = \frac{1}{2\pi} \left[\frac{x^2}{2}\right]_0^{2\pi} = \pi.
$$

For $n \ne 0$, we use integration by parts with $u=x$ and $dv=e^{-inx}dx$.

$$
\begin{align*}
c_n[f] &= \frac{1}{2\pi} \int_0^{2\pi} x e^{-inx} dx \\
&= \frac{1}{2\pi} \left( \left[ x \frac{e^{-inx}}{-in} \right]_0^{2\pi} - \int_0^{2\pi} \frac{e^{-inx}}{-in} dx \right) \\
&= \frac{1}{2\pi} \left( \frac{2\pi e^{-in2\pi}}{-in} - 0 - \left[ \frac{e^{-inx}}{(-in)^2} \right]_0^{2\pi} \right) \\
&= \frac{1}{2\pi} \left( \frac{2\pi}{-in} - 0 \right) \\
$= \frac{1}{-in} \\
$= \frac{i}{n}.
\end{align*}
$$

The Fourier series is

$$
S[f](x) = \pi + \sum_{n \in \mathbb{Z}, n \ne 0} \frac{i}{n} e^{inx}.
$$

The function $f$ is piecewise smooth. For any $x \in (0, 2\pi)$, $f$ is continuous, so by Dirichlet's Theorem, $S[f](x) = f(x) = x$.
At the discontinuity $x=0$, we have $f(0^+) = \lim_{t \to 0^+} f(t) = 0$ and $f(0^-) = \lim_{t \to 2\pi^-} f(t) = 2\pi$. The series converges to the midpoint:

$$
S[f](0) = \frac{f(0^+) + f(0^-)}{2} = \frac{0 + 2\pi}{2} = \pi.
$$

This matches the value of the constant term in the series.
$\square$
