---
title: Hypersurface vs. Hyperslice
description: A formal definition of hypersurfaces in affine, projective, and quasiprojective varieties, distinguishing them from general zero sets (hyperslices).
date: 2025-10-01T00:04:45+00:00
---

**Hyperslices and Hypersurfaces in Affine Space.**

Let $K$ be an algebraically closed field and let $\mathbb{A}^n$ be the $n$-dimensional affine space over $K$. The distinction between a general zero set of a single polynomial and a proper, non-empty one is formalized algebraically.

**Definition (Affine Hyperslice).**
For any polynomial $f \in K[x_1, \dots, x_n]$, the ***affine hyperslice*** defined by $f$ is the affine variety $V(f) \subseteq \mathbb{A}^n$.

**Definition (Affine Hypersurface).**
An affine variety $X \subseteq \mathbb{A}^n$ is an ***affine hypersurface*** if $X = V(f)$ for some non-constant polynomial $f \in K[x_1, \dots, x_n]$. This is equivalent to $f$ being neither a unit (a non-zero constant) nor the zero element in $K[x_1, \dots, x_n]$.

**Theorem (Hyperslices vs. Hypersurfaces in Affine Space).**
Let $f \in K[x_1, \dots, x_n]$. The hyperslice $V(f)$ has the following properties:
1. $V(f) = \emptyset$ if and only if $f$ is a non-zero constant.
2. $V(f) = \mathbb{A}^n$ if and only if $f = 0$.

*Proof.* The identities $V(1) = \emptyset$ and $V(0) = \mathbb{A}^n$ are immediate. Conversely, if $V(f) = \emptyset$, the Nullstellensatz implies that the ideal $\langle f \rangle$ is $K[x_1, \dots, x_n]$, so $1 \in \langle f \rangle$, which means $f$ is a unit. If $V(f) = \mathbb{A}^n$, then $f$ vanishes on all points; since $K$ is infinite, this implies $f=0$. $\square$

**Hypersurfaces on an Irreducible Affine Variety.**

Let $X \subseteq\mathbb{A}^n$ be an irreducible affine variety with coordinate ring $K[X]$.

**Definition (Hyperslice on a Variety).**
For any regular function $f \in K[X]$, the ***hyperslice*** defined by $f$ is the set $V_X(f) = \{x \in X \mid f(x) = 0\}$. This is a Zariski-closed subset of $X$.

**Definition (Hypersurface on a Variety).**
A hyperslice $V_X(f)$ is a ***hypersurface in $X$*** if $f$ is neither a unit nor the zero element in the coordinate ring $K[X]$.

**Theorem (Hyperslices vs. Hypersurfaces on an Irreducible Affine Variety).**
Let $X$ be an irreducible affine variety and $f \in K[X]$. Then:
1. $V_X(f) = \emptyset$ if and only if $f$ is a unit in $K[X]$.
2. $V_X(f) = X$ if and only if $f = 0$ in $K[X]$.

*Proof.* A regular function has no zeros on $X$ if and only if it is invertible in the ring of functions $K[X]$, making it a unit. Since $X$ is irreducible, $K[X]$ is an integral domain, so $f=0$ is the only function that vanishes everywhere on $X$. $\square$

**Hypersurfaces in Projective Space.**

Let $F$ be a homogeneous polynomial in the ring $K[x_0, \dots, x_n]$.

**Definition (Projective Hyperslice).**
For a homogeneous polynomial $F \in K[x_0, \dots, x_n]$, the ***projective hyperslice*** defined by $F$ is the projective variety $V(F) \subseteq \mathbb{P}^n$.

**Definition (Projective Hypersurface).**
A projective variety $X \subseteq \mathbb{P}^n$ is a ***projective hypersurface*** if $X = V(F)$ for some non-constant homogeneous polynomial $F$ (i.e., $\operatorname{deg}(F) \ge 1$).

**Theorem (Hyperslices vs. Hypersurfaces in Projective Space).**
Let $F \in K[x_0, \dots, x_n]$ be a homogeneous polynomial.
1. $V(F) = \emptyset$ if and only if $F$ is a non-zero constant.
2. $V(F) = \mathbb{P}^n$ if and only if $F = 0$.

*Proof.* By the projective Nullstellensatz, $V(F) = \emptyset$ if and only if the ideal $\langle F \rangle$ contains all homogeneous polynomials of some sufficiently high degree. This occurs only if $F$ is a unit (a non-zero constant). The second statement is direct. For any non-constant $F$, $V(F)$ is non-empty. $\square$

**Local Hypersurfaces in Quasiprojective Varieties.**

Let $X$ be an irreducible quasiprojective variety.

**Definition (Local Hyperslice).**
A subset $Y \subseteq X$ is a ***local hyperslice*** if for every point $p \in X$, there exists an open neighborhood $U \subseteq X$ of $p$ and a regular function $F \in K[U]$ such that $Y \cap U = V(F)$. This condition implies that $Y$ is a closed subvariety of $X$.

**Definition (Local Hypersurface).**
A nonempty closed subvariety $Y \subseteq X$ is a ***local hypersurface*** if for every point $p \in X$, there exists an open neighborhood $U \subseteq X$ of $p$ and a regular function $F \in K[U]$ such that $F$ does not vanish on any irreducible component of $U$ and $Y \cap U = V(F)$.

**Theorem (Local Hyperslices vs. Local Hypersurfaces).**
Let $Y \subseteq X$ be a local hyperslice. Let $\{U_i\}$ be an open cover of $X$ such that for each $i$, $Y \cap U_i = V(F_i)$ for some $F_i \in K[U_i]$. Then:
1. $Y = \emptyset$ if and only if for every $i$, $F_i$ is a unit in $K[U_i]$.
2. $Y = X$ if and only if for every $i$, $F_i = 0$ in $K[U_i]$.

*Proof.* As being closed is a local property, $Y$ is closed in $X$. For (1), if $Y = \emptyset$, then $Y \cap U_i = \emptyset = V(F_i)$ for each $i$. Since each $U_i$ can be covered by affine open sets, this implies $F_i$ is locally a unit, and thus a unit in $K[U_i]$. The converse is immediate. For (2), if $Y=X$, then $Y \cap U_i = U_i = V(F_i)$, which implies $F_i = 0$ in $K[U_i]$ for all $i$. The converse is immediate. $\square$