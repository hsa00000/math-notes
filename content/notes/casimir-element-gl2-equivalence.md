---
title: Equivalence of Casimir Element Expressions for gl₂(ℝ)
description: A proof demonstrating the equivalence of two standard formulas for the quadratic Casimir element of the general linear Lie algebra gl₂(ℝ).
---

**Definition 1 (Standard Basis and Casimir Element).**
Let the Lie algebra $\mathfrak{gl}_2(\mathbb{R})$ be spanned by the standard basis over $\mathbb{R}$:

$$
H = \begin{pmatrix} 1 & 0 \\ 0 & -1 \end{pmatrix}, \quad E = \begin{pmatrix} 0 & 1 \\ 0 & 0 \end{pmatrix}, \quad F = \begin{pmatrix} 0 & 0 \\ 1 & 0 \end{pmatrix}, \quad I = \begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix}.
$$

The element $I$ spans the center of $\mathfrak{gl}_2(\mathbb{R})$. The quadratic Casimir element derived from the trace form on $\mathfrak{gl}_2(\mathbb{R})$ is the element **_$\Omega_{\text{std}}$_** in the universal enveloping algebra $U(\mathfrak{gl}_2(\mathbb{R}))$ given by:

$$
\Omega_{\text{std}} = \frac{1}{2}H^2 + EF + FE + \frac{1}{2}I^2.
$$

**Definition 2 (Alternative Basis and Casimir Element).**
Let $\mathfrak{gl}_2(\mathbb{R})$ be spanned by the alternative basis:

$$
X = \begin{pmatrix} 1 & 0 \\ 0 & -1 \end{pmatrix}, \quad Y = \begin{pmatrix} 0 & 1 \\ 1 & 0 \end{pmatrix}, \quad K = \begin{pmatrix} 0 & 1 \\ -1 & 0 \end{pmatrix}, \quad I = \begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix}.
$$

Within the complexified universal enveloping algebra $U(\mathfrak{gl}_2(\mathbb{C}))$, we define the **_raising operator $R$_** and **_lowering operator $L$_** as $R = \frac{1}{2}(X+iY)$ and $L = \frac{1}{2}(X-iY)$. An alternative expression for the Casimir element is the element **_$\Omega_{\text{alt}}$_** given by:

$$
\Omega_{\text{alt}} = -\frac{1}{2}K^2 + RL + LR + \frac{1}{2}I^2.
$$

**Theorem 1 (Equivalence of Casimir Formulations for $\mathfrak{gl}_2(\mathbb{R})$).**
The two formulations of the quadratic Casimir element are equal.

$$
\Omega_{\text{std}} = \Omega_{\text{alt}}.
$$

_Proof._
The elements of the two bases are related by the following linear transformations: $X=H$, $Y=E+F$, and $K=E-F$. The products $E^2$ and $F^2$ are zero in the algebra of matrices, and thus also in $U(\mathfrak{gl}_2(\mathbb{R}))$. The calculation proceeds by expressing $\Omega_{\text{alt}}$ in the standard basis $\{H, E, F, I\}$.

$$
\begin{align*}
\Omega_{\text{alt}} &= -\frac{1}{2}K^2 + RL + LR + \frac{1}{2}I^2 \\
&= -\frac{1}{2}K^2 + \frac{1}{4}(X+iY)(X-iY) + \frac{1}{4}(X-iY)(X+iY) + \frac{1}{2}I^2 \\
&= -\frac{1}{2}K^2 + \frac{1}{4}(X^2 + Y^2 + i[Y,X]) + \frac{1}{4}(X^2 + Y^2 - i[Y,X]) + \frac{1}{2}I^2 \\
&= -\frac{1}{2}K^2 + \frac{1}{2}(X^2 + Y^2) + \frac{1}{2}I^2 \\
&= -\frac{1}{2}(E-F)^2 + \frac{1}{2}\left(H^2 + (E+F)^2\right) + \frac{1}{2}I^2 \\
&= -\frac{1}{2}(E^2 - EF - FE + F^2) + \frac{1}{2}(H^2 + E^2 + EF + FE + F^2) + \frac{1}{2}I^2 \\
&= -\frac{1}{2}(-EF-FE) + \frac{1}{2}(H^2 + EF+FE) + \frac{1}{2}I^2 \\
&= \frac{1}{2}(EF+FE) + \frac{1}{2}H^2 + \frac{1}{2}(EF+FE) + \frac{1}{2}I^2 \\
&= \frac{1}{2}H^2 + EF + FE + \frac{1}{2}I^2 \\
&= \Omega_{\text{std}}.
\end{align*}
$$

$\square$
