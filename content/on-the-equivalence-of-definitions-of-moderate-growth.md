---
title: Equivalence of Moderate Growth Definitions on GL(2,R) and SL(2,R)
description: An analysis of the equivalence between two definitions of moderate growth for functions on GL(2,R) and SL(2,R), showing equivalence holds on SL(2,R) but not on GL(2,R) due to the behavior of the determinant.
---

**Definition 1.**

Let $G$ be a matrix group. For $g \in G$, let $\|g\|_{HS}$ be the Hilbert-Schmidt norm defined by $\|g\|_{HS}^2 = \operatorname{tr}(g^t g)$. A function $f: G \to \mathbb{C}$ is of **_moderate growth with respect to the Hilbert-Schmidt norm_** if there exist constants $C > 0$ and $N \in \mathbb{N}$ such that for all $g \in G$,

$$
|f(g)| \leq C \|g\|_{HS}^N
$$

**Definition 2.**

Let $G$ be a matrix group. For $g \in G$, let $\|g\|_{\text{max}}$ be the norm defined by $\|g\|_{\text{max}} = \max \{ |g_{ij}|, |(g^{-1})_{ij}| \}_{i,j}$. A function $f: G \to \mathbb{C}$ is of **_moderate growth with respect to the max-entry norm_** if there exist constants $C > 0$ and $N \in \mathbb{N}$ such that for all $g \in G$,

$$
|f(g)| \leq C \|g\|_{\text{max}}^N
$$

**Theorem 1 (Equivalence Principle).**

The two definitions of moderate growth are equivalent for a function $f: G \to \mathbb{C}$ if and only if the norms $\| \cdot \|_{HS}$ and $\| \cdot \|_{\text{max}}$ are polynomially equivalent on the matrix group $G$.

_Proof._
Suppose there exist constants $C_1, C_2 > 0$ and exponents $p_1, p_2 \in \mathbb{N}$ such that for all $g \in G$, $\|g\|_{HS} \leq C_1 \|g\|_{\text{max}}^{p_1}$ and $\|g\|_{\text{max}} \leq C_2 \|g\|_{HS}^{p_2}$. If $f$ is of moderate growth with respect to $\| \cdot \|_{HS}$, then $|f(g)| \leq C \|g\|_{HS}^N \leq C (C_1 \|g\|_{\text{max}}^{p_1})^N = (C C_1^N) \|g\|_{\text{max}}^{N p_1}$. This shows $f$ is of moderate growth with respect to $\| \cdot \|_{\text{max}}$. The converse follows symmetrically by exchanging the roles of the norms. Thus, the equivalence of the definitions is equivalent to the polynomial equivalence of the norms.
$\square$

**Theorem 2 (Norm Equivalence on GL(2,R) and SL(2,R)).**

(i) On $G=GL(2, \mathbb{R})$, the norms $\| \cdot \|_{HS}$ and $\| \cdot \|_{\text{max}}$ are not polynomially equivalent.
(ii) On $G=SL(2, \mathbb{R})$, the norms $\| \cdot \|_{HS}$ and $\| \cdot \|_{\text{max}}$ are polynomially equivalent.

_Proof._
Let $g = \begin{pmatrix} a & b \\ c & d \end{pmatrix} \in GL(2, \mathbb{R})$. First, we establish an inequality in one direction. The definition of the max-entry norm implies $\max\{|a|,|b|,|c|,|d|\} \leq \|g\|_{\text{max}}$.

$$
\|g\|_{HS}^2 = a^2+b^2+c^2+d^2 \leq 4 (\max\{|a|,|b|,|c|,|d|\})^2 \leq 4 \|g\|_{\text{max}}^2
$$

This yields $\|g\|_{HS} \leq 2 \|g\|_{\text{max}}$, which holds for any subgroup of $GL(2, \mathbb{R})$.

For the reverse inequality, we must bound $\|g\|_{\text{max}}$ by a polynomial in $\|g\|_{HS}$. This requires bounding the entries of both $g$ and $g^{-1}$. The entries of $g$ are bounded by its Hilbert-Schmidt norm, since $|g_{ij}|^2 \leq \sum_{k,l} |g_{kl}|^2 = \|g\|_{HS}^2$, which implies $|g_{ij}| \leq \|g\|_{HS}$. For the inverse,

$$
g^{-1} = \frac{1}{\det g} \begin{pmatrix} d & -b \\ -c & a \end{pmatrix}
$$

The magnitudes of the entries of $g^{-1}$ are of the form $|g_{kl}|/|\det g|$. Since $|g_{kl}| \leq \|g\|_{HS}$, any polynomial bound on $\|g\|_{\text{max}}$ relies on a polynomial upper bound for $1/|\det g|$ in terms of $\|g\|_{HS}$.

(i) For $G = GL(2, \mathbb{R})$, such a bound does not exist. Consider the sequence $g_n = \begin{pmatrix} 1/n & 0 \\ 0 & 1 \end{pmatrix}$ for $n \in \mathbb{N}, n \ge 1$. The Hilbert-Schmidt norm is bounded: $\|g_n\|_{HS}^2 = (1/n)^2 + 1^2 \leq 2$. However, $|\det g_n| = 1/n$. Then $\|g_n\|_{\text{max}} = \max\{1/n, 1, n, 0\} = n$. The sequence $\|g_n\|_{\text{max}}$ is unbounded while $\|g_n\|_{HS}$ is bounded. No inequality of the form $\|g\|_{\text{max}} \leq C_2 \|g\|_{HS}^{p_2}$ can hold for all $g \in GL(2, \mathbb{R})$.

(ii) For $G = SL(2, \mathbb{R})$, we have $|\det g| = 1$. The entries of $g^{-1}$ are the entries of the adjugate matrix, which are $\pm a, \pm b, \pm c, \pm d$. The maximum absolute entry of $g^{-1}$ is $\max\{|a|,|b|,|c|,|d|\}$. Therefore,

$$
\|g\|_{\text{max}} = \max \{ |g_{ij}|, |(g^{-1})_{ij}| \} = \max\{|a|,|b|,|c|,|d|\}
$$

Since $|g_{ij}| \leq \|g\|_{HS}$ for all $i,j$, we have $\|g\|_{\text{max}} \leq \|g\|_{HS}$. Combined with $\|g\|_{HS} \leq 2 \|g\|_{\text{max}}$, the norms are polynomially equivalent on $SL(2, \mathbb{R})$.
$\square$
