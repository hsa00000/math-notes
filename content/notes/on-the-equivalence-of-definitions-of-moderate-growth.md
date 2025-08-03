---
title: On the Equivalence of Definitions of Moderate Growth
description: A proof investigating the equivalence of two common definitions for moderate growth of functions on GL(2, R), one based on the Hilbert-Schmidt norm and the other on a max-entry norm that includes the inverse.
---

**Definition 1 (Hilbert-Schmidt Moderate Growth).**

Let $G$ be a matrix group, and for $g \in G$, let $\|g\|_{HS}$ be the Hilbert-Schmidt norm defined by $\|g\|_{HS}^2 = \operatorname{tr}(g^t g)$. A function $f: G \to \mathbb{C}$ is of **_moderate growth with respect to the Hilbert-Schmidt norm_** if there exist constants $C > 0$ and $N \in \mathbb{N}$ such that for all $g \in G$,

$$
|f(g)| \leq C \|g\|_{HS}^N
$$

**Definition 2 (Max-Entry Moderate Growth).**

Let $G$ be a matrix group. For $g \in G$, let $\|g\|_{\text{max}}$ be the norm defined by $\|g\|_{\text{max}} = \max \{ |g_{ij}|, |(g^{-1})_{ij}| \}_{i,j}$. A function $f: G \to \mathbb{C}$ is of **_moderate growth with respect to the max-entry norm_** if there exist constants $C > 0$ and $N \in \mathbb{N}$ such that for all $g \in G$,

$$
|f(g)| \leq C \|g\|_{\text{max}}^N
$$

**Theorem 1 (Analysis of Equivalence for $GL(2, \mathbb{R})$).**

The two definitions of moderate growth are equivalent if and only if the norms $\|g\|_{HS}$ and $\|g\|_{\text{max}}$ are polynomially equivalent on $G=GL(2, \mathbb{R})$.

_Proof._
The equivalence of the two definitions requires that a function satisfying one growth condition also satisfies the other. Suppose there exist constants $C_1, C_2 > 0$ and exponents $p_1, p_2 \in \mathbb{N}$ such that for all $g \in G$,

$$
\|g\|_{HS} \leq C_1 \|g\|_{\text{max}}^{p_1} \quad \text{and} \quad \|g\|_{\text{max}} \leq C_2 \|g\|_{HS}^{p_2}
$$

If $f$ satisfies Definition 1, then $|f(g)| \leq C \|g\|_{HS}^N \leq C (C_1 \|g\|_{\text{max}}^{p_1})^N = (C C_1^N) \|g\|_{\text{max}}^{N p_1}$. This implies $f$ satisfies Definition 2. If $f$ satisfies Definition 2, then $|f(g)| \leq C \|g\|_{\text{max}}^N \leq C (C_2 \|g\|_{HS}^{p_2})^N = (C C_2^N) \|g\|_{HS}^{N p_2}$. This implies $f$ satisfies Definition 1. Thus, the equivalence of the definitions is contingent upon the polynomial equivalence of the norms. We now investigate this equivalence for $G = GL(2, \mathbb{R})$.

Let $g = \begin{pmatrix} a & b \\ c & d \end{pmatrix} \in GL(2, \mathbb{R})$. The first inequality, $\|g\|_{HS} \leq C_1 \|g\|_{\text{max}}^{p_1}$, holds. The entries of $g$ are bounded by $\|g\|_{\text{max}}$ by definition.

$$
\|g\|_{HS}^2 = a^2+b^2+c^2+d^2 \leq 4 (\max\{|a|,|b|,|c|,|d|\})^2 \leq 4 \|g\|_{\text{max}}^2
$$

This yields $\|g\|_{HS} \leq 2 \|g\|_{\text{max}}$, satisfying the condition with $C_1=2, p_1=1$.

The second inequality, $\|g\|_{\text{max}} \leq C_2 \|g\|_{HS}^{p_2}$, requires bounding the entries of both $g$ and $g^{-1}$ by a polynomial in $\|g\|_{HS}$. For the entries of $g$, we have $|g_{ij}| \leq \|g\|_{HS}$. For the entries of $g^{-1}$, we have

$$
g^{-1} = \frac{1}{\det g} \begin{pmatrix} d & -b \\ -c & a \end{pmatrix}
$$

The absolute values of the entries of $g^{-1}$ are of the form $|g_{kl}|/|\det g|$. Since $|g_{kl}| \leq \|g\|_{HS}$, the inequality hinges on establishing an upper bound for $1/|\det g|$ that is polynomial in $\|g\|_{HS}$.

Such a bound does not exist for $g \in GL(2, \mathbb{R})$. Consider the sequence of matrices $g_n \in GL(2, \mathbb{R})$ for $n \in \mathbb{N}, n \ge 1$:

$$
g_n = \begin{pmatrix} 1/n & 0 \\ 0 & 1 \end{pmatrix}
$$

The Hilbert-Schmidt norm of this sequence is bounded: $\|g_n\|_{HS}^2 = (1/n)^2 + 1^2 \leq 2$. However, the determinant is $|\det g_n| = 1/n$. The term $1/|\det g_n| = n$ is not bounded by any polynomial in the bounded sequence $\|g_n\|_{HS}$. Consequently, $\|g_n\|_{\text{max}} = \max\{1, 1/n, n, 0\} = n$, which cannot be bounded by $C_2 \|g_n\|_{HS}^{p_2}$ for any fixed $C_2, p_2$.

The definitions are therefore not equivalent on $GL(2, \mathbb{R})$. The Hilbert-Schmidt norm fails to detect movement towards singularity, whereas the max-entry norm, by including the inverse, is sensitive to it. For groups such as $SL(n, \mathbb{R})$ where $|\det g|=1$, the entries of the inverse are polynomially bounded by the entries of the original matrix, and the equivalence holds.
$\square$
