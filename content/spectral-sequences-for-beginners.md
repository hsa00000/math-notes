---
title: Spectral Sequences for Beginners
description: A detailed introduction to the spectral sequence of a filtered complex and its application to double complexes.
---

**Introduction.**

A spectral sequence is a computational tool in homological algebra for computing the homology of a complex by approximation. The primary input is a filtration on a complex, which decomposes it into a sequence of simpler pieces. The spectral sequence is organized into "pages," where each page is the homology of the previous one. This process iteratively refines homological information to reveal the structure of the homology of the original complex.

**Definition.**

Let $(K_*, d)$ be a chain complex. A ***subcomplex*** of $K_*$ is a sequence of subobjects $A_n \subseteq K_n$ for each integer $n$ such that the differential of $K_*$ restricts to a differential on $A_*$. This means that for every $n$, the image of $A_n$ under the differential $d_n: K_n \to K_{n-1}$ is contained within $A_{n-1}$; that is, $d(A_n) \subseteq A_{n-1}$. The differential of the subcomplex $(A_*, d|_A)$ is the restriction of $d$ to $A_*$.

**Definition.**

A ***filtered complex*** is a chain complex $(K_*, d)$ equipped with a family of subcomplexes $\{F_p K_*\}_{p \in \mathbb{Z}}$ such that:

$$
\dots \subseteq F_{p-1} K_* \subseteq F_p K_* \subseteq F_{p+1} K_* \subseteq \dots
$$

The filtration is ***exhaustive*** if $\bigcup_p F_p K_* = K_*$ and ***bounded*** if for each degree $n$, there exist $p_{min}$ and $p_{max}$ such that $F_{p_{min}} K_n = 0$ and $F_{p_{max}} K_n = K_n$.

**The Pages of the Spectral Sequence.**

**Definition.**

The ***zeroth page*** ($E^0$) is the associated graded object of the filtered complex. Its terms are defined as the quotients of successive filtration levels:

$$
E^0_{p,q} := \frac{F_p K_{p+q}}{F_{p-1} K_{p+q}}
$$

The index $p$ is the filtration degree, and $n=p+q$ is the homological degree. The differential $d^0: E^0_{p,q} \to E^0_{p,q-1}$ is induced by the complex's differential $d$. For an element $[x] \in E^0_{p,q}$ represented by $x \in F_p K_{p+q}$, we define $d^0([x]) = [d(x)]$. This is well-defined because $F_p K_*$ is a subcomplex, so $d(x) \in F_p K_{p+q-1}$, and its image in the quotient $F_p K_{p+q-1} / F_{p-1} K_{p+q-1}$ is independent of the choice of representative for $[x]$.

**Definition.**

The ***first page*** ($E^1$) is the homology of the zeroth page with respect to $d^0$:

$$
E^1_{p,q} := H_{p,q}(E^0, d^0) = \frac{\ker(d^0: E^0_{p,q} \to E^0_{p,q-1})}{\operatorname{im}(d^0: E^0_{p,q+1} \to E^0_{p,q})}
$$

The differential $d^1: E^1_{p,q} \to E^1_{p-1,q}$ is induced by $d$. An element in $E^1_{p,q}$ is a class represented by $x \in F_p K_{p+q}$ such that $d(x) \in F_{p-1} K_{p+q-1}$. The map is defined by sending the class of $x$ to the class of $d(x)$ in the appropriate homology group, $E^1_{p-1,q}$. This map has bidegree $(-1, 0)$.

**Definition.**

The ***r-th page*** ($E^r$) is defined recursively, with the page $(E^{r+1}, d^{r+1})$ being the homology of the page $(E^r, d^r)$.

$$
E^{r+1}_{p,q} := H_{p,q}(E^r, d^r)
$$

The differential $d^r: E^r_{p,q} \to E^r_{p-r, q+r-1}$ has bidegree $(-r, r-1)$. It is induced by $d$ on elements whose images under $d$ "jump down" $r$ filtration levels.

**Convergence of the Spectral Sequence.**

**Definition.**

A filtration on a complex $(K_*, d)$ induces a filtration on its homology. The ***p-th filtration of the homology*** is defined as the image of the homology of the subcomplex $F_p K_*$ inside the homology of the total complex:

$$
F_p H_n(K_*) := \operatorname{im}\left( H_n(F_p K_*) \to H_n(K_*) \right)
$$

**Definition.**

For a given bidegree $(p,q)$, the sequence of differentials $d^r_{p,q}$ eventually maps to or from a zero object if the filtration is bounded. This implies the sequence of groups $E^r_{p,q}$ stabilizes for large $r$. This stable group is called the ***infinity page***, denoted $E^\infty_{p,q}$.

**Definition.**

A spectral sequence ***converges*** to $H_*(K_*)$, denoted $E^2_{p,q} \implies H_{p+q}(K_*)$, if the infinity page is isomorphic to the associated graded object of the filtered homology. Formally, for all $p,q$:

$$
E^\infty_{p,q} \cong \frac{F_p H_{p+q}(K_*)}{F_{p-1} H_{p+q}(K_*)}
$$

This means the terms on the infinity page are the successive "pieces" of the filtered homology groups of the original complex.

**Theorem.**

Let $C_{p,q}$ be a double complex of $R$-modules which is zero outside the first quadrant ($p,q \ge 0$). Let $K_* = \operatorname{Tot}(C)$ be its total complex. There are two canonical filtrations on $K_*$, each giving rise to a spectral sequence that converges to $H_*(K_*)$.

*Proof.*
The total complex has terms $K_n = \bigoplus_{p+q=n} C_{p,q}$ and differential $d = d^h + d^v$.

Case 1: Filtration by Row Index (Column-First Calculation).
Define the filtration $'F_p K_n := \bigoplus_{i \le p, i+j=n} C_{i,j}$.
The zeroth page is $'E^0_{p,q} \cong C_{p,q}$, and its differential $d^0$ is the vertical differential $d^v$.
The first page is the homology of the columns: $'E^1_{p,q} = H_q(C_{p,*}, d^v)$.
The differential $d^1$ on $'E^1$ is induced by the horizontal differential $d^h$. The second page is the homology of the resulting complex of column homologies:

$$
'E^2_{p,q} = H_p(H_q(C, d^v), d^h)
$$

This spectral sequence converges: $'E^2_{p,q} \implies H_{p+q}(K_*)$.

Case 2: Filtration by Column Index (Row-First Calculation).
Define the filtration $''F_q K_n := \bigoplus_{j \le q, i+j=n} C_{i,j}$.
The zeroth page is $''E^0_{p,q} \cong C_{p,q}$, and its differential $d^0$ is the horizontal differential $d^h$.
The first page is the homology of the rows: $''E^1_{p,q} = H_p(C_{*,q}, d^h)$.
The differential $d^1$ on $''E^1$ is induced by the vertical differential $d^v$. The second page is the homology of the resulting complex of row homologies:

$$
''E^2_{p,q} = H_q(H_p(C, d^h), d^v)
$$

This spectral sequence also converges: $''E^2_{p,q} \implies H_{p+q}(K_*)$.

Since both spectral sequences converge to $H_*(K_*)$, their abutments are isomorphic. In many applications, such as the proof that the Tor functor is balanced, the spectral sequences ***collapse at the $E^2$ page***. This occurs when all higher differentials $d^r$ for $r \ge 2$ are zero. For a first-quadrant double complex, this happens if the $E^2$ page has non-zero terms only on a single row or a single column. In that case, $E^2 \cong E^\infty$, which provides a direct isomorphism between the two iterated homology computations.
$\square$