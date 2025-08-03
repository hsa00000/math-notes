---
title: Fourier Series Convergence for Piecewise Smooth Functions
description: This note establishes the convergence criteria for Fourier series of piecewise smooth functions, with a specific focus on the behavior at points of continuity and at jump discontinuities.
---

**0. Preliminaries: A Broader Class of Functions.**

**Definition.**
A function $f$ is ***piecewise continuous*** on a finite interval $[a, b]$ if it is continuous at every point in $[a, b]$ except for a finite number of points $x_i$, at each of which the left-hand and right-hand limits, denoted $f(x_i^-) = \lim_{t \to x_i^-} f(t)$ and $f(x_i^+) = \lim_{t \to x_i^+} f(t)$, exist and are finite.

**Definition.**
A function $f$ is ***piecewise smooth*** on an interval if both the function $f$ and its derivative $f'$ are piecewise continuous on that interval. A periodic function is piecewise smooth if it is piecewise smooth on any finite interval of one period.

**1. Pointwise Convergence Theorem for Piecewise Smooth Functions.**

The following theorem provides a definitive statement on the pointwise convergence behavior of a Fourier series for a function that is well-behaved between a finite number of jump discontinuities.

**Theorem 1 (Dirichlet's Convergence Theorem).**
Let $f: \mathbb{R} \to \mathbb{C}$ be a $2\pi$-periodic and piecewise smooth function. The Fourier series of $f$, denoted $S[f](x)$, converges for all $x \in \mathbb{R}$. The limit of the series is as follows:
1. At any point $x$ where $f$ is continuous, the series converges to the value of the function: $S[f](x) = f(x)$.
2. At any point of discontinuity $x_0$, the series converges to the arithmetic mean of the left-hand and right-hand limits:

$$
S[f](x_0) = \frac{f(x_0^+) + f(x_0^-)}{2}
$$

*Proof.*
The $N$-th symmetric partial sum of the Fourier series, $S_N[f](x)$, is the convolution of $f$ with the Dirichlet kernel $D_N(t) = \sum_{k=-N}^{N} e^{ikt} = \frac{\sin((N + 1/2)t)}{\sin(t/2)}$. Let $L(x)$ be the asserted limit.

$$
S_N[f](x) - L(x) = \frac{1}{2\pi} \int_{-\pi}^{\pi} (f(x-t) - L(x)) D_N(t) \,dt
$$

The integral is split at $t=0$, and a change of variable $u=-t$ is applied to the integral over $[-\pi, 0]$.

$$
\int_{-\pi}^{0} \frac{f(x-t)-L(x)}{\sin(t/2)} \sin\left(\left(N+\frac{1}{2}\right)t\right)dt = \int_{0}^{\pi} \frac{f(x+u)-L(x)}{\sin(u/2)} \sin\left(\left(N+\frac{1}{2}\right)u\right)du
$$

Combining this with the integral over $[0, \pi]$ yields:

$$
S_N[f](x) - L(x) = \frac{1}{2\pi} \int_0^\pi \frac{f(x+t) + f(x-t) - 2L(x)}{\sin(t/2)} \sin\left(\left(N+\frac{1}{2}\right)t\right) dt
$$

Let $h(t) = \frac{f(x+t) + f(x-t) - 2L(x)}{\sin(t/2)}$. For the Riemann-Lebesgue Lemma to apply, $h(t)$ must be integrable on $[0, \pi]$. The only point of concern is the behavior as $t \to 0^+$. The limit is an indeterminate form $\frac{0}{0}$ because $\lim_{t \to 0^+} (f(x+t) + f(x-t) - 2L(x)) = f(x^+) + f(x^-) - 2L(x) = 0$. By L'Hôpital's rule:

$$
\lim_{t \to 0^+} h(t) = \lim_{t \to 0^+} \frac{f'(x+t) - f'(x-t)}{\frac{1}{2}\cos(t/2)} = \frac{f'(x^+) - f'(x^-)}{1/2} = 2(f'(x^+) - f'(x^-))
$$

Since $f$ is piecewise smooth, $f'$ is piecewise continuous. Thus, the one-sided limits $f'(x^+)$ and $f'(x^-)$ are finite, which implies $\lim_{t \to 0^+} h(t)$ is finite. Therefore, $h(t)$ is integrable on $[0, \pi]$. The Riemann-Lebesgue Lemma states that $\lim_{N \to \infty} \int_0^\pi h(t) \sin(((N+1/2))t) dt = 0$. Consequently, $\lim_{N \to \infty} (S_N[f](x) - L(x)) = 0$. $\square$

**2. Example: The Sawtooth Wave.**

Consider the function $f(x)=x$ on the interval $[0, 2\pi)$, extended periodically to all of $\mathbb{R}$. This function has jump discontinuities at every $x = 2k\pi$ for $k \in \mathbb{Z}$. The Fourier coefficients are computed on $[0, 2\pi)$. The constant term is $c_0 = \pi$. For $n \ne 0$, integration by parts gives:

$$
\begin{align*}
c_n[f] &= \frac{1}{2\pi} \int_0^{2\pi} x e^{-inx} dx \\
&= \frac{1}{2\pi} \left( \left[ x \frac{e^{-inx}}{-in} \right]_0^{2\pi} - \int_0^{2\pi} \frac{e^{-inx}}{-in} dx \right) \\
&= \frac{1}{2\pi} \left( \frac{2\pi}{-in} - \left[ \frac{e^{-inx}}{(-in)^2} \right]_0^{2\pi} \right) \\
&= \frac{1}{-in} - 0 = \frac{i}{n}
\end{align*}
$$

The Fourier series is $S[f](x) = \pi + \sum_{n \in \mathbb{Z}, n \ne 0} \frac{i}{n} e^{inx}$. The function $f$ is piecewise smooth. For any $x \in (0, 2\pi)$, $f$ is continuous, so $S[f](x) = f(x) = x$. At the discontinuity $x=0$, the left and right limits are $f(0^-) = 2\pi$ and $f(0^+) = 0$. By Dirichlet's Theorem, the series converges to the midpoint:

$$
S[f](0) = \frac{f(0^+) + f(0^-)}{2} = \frac{0 + 2\pi}{2} = \pi
$$

This value matches the constant term of the series. $\square$