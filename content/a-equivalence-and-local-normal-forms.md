---
title: A-Equivalence and Local Normal Forms of Smooth Maps
description: Defines A-equivalence for smooth map-germs and uses it to characterize immersions and submersions via local normal forms, showing its equivalence to the classical rank-based definitions and its application to submanifolds.
date: 2025-09-10T03:59:00+00:00
---

**Definition (Smooth Map-Germ).**

Let $M$ and $N$ be smooth manifolds, $p \in M$, and $q \in N$. An equivalence relation is defined on the set of smooth maps $f: U \to N$, where $U$ is any open neighborhood of $p$. Two maps $f_1: U_1 \to N$ and $f_2: U_2 \to N$ are equivalent if there exists an open neighborhood $W \subseteq U_1 \cap U_2$ of $p$ such that $f_1|_W = f_2|_W$. An equivalence class $[f]$ is a ***smooth map-germ*** from $(M, p)$ to $(N, q)$, where $f(p) = q$.

*Intuition: A map-germ captures the behavior of a function in an infinitesimally small neighborhood of a point, discarding any information about the function's behavior far from that point.*

**Definition (A-Equivalence).**

Let $f, g: (M, p) \to (N, q)$ be two smooth map-germs. They are ***A-equivalent*** (or right-left equivalent) if there exist diffeomorphism-germs $\phi: (M, p) \to (M, p)$ and $\psi: (N, q) \to (N, q)$ such that the relation $\psi \circ f = g \circ \phi$ holds for representatives in a neighborhood of $p$.

*Intuition: A-equivalence formalizes the idea of two functions having the same "local structure" up to a smooth change of coordinates in both the source (domain) and the target (codomain). The diffeomorphisms $\phi$ and `ψ` act as these local coordinate changes.*

**Definition (Standard Normal Forms).**

Let $m, n, r$ be non-negative integers.
1.  The ***standard rank-r map*** is the map $\rho_r: \mathbb{R}^m \to \mathbb{R}^n$ given by
    $$
    \rho_r(x_1, \dots, x_m) = (x_1, \dots, x_r, 0, \dots, 0).
    $$
2.  The ***standard projection*** is the case where $r=n \leq m$, denoted $\pi = \rho_n$.
3.  The ***standard inclusion*** is the case where $r=m \leq n$, denoted $\iota = \rho_m$.

**Definition (Immersion and Submersion via A-Equivalence).**

Let $f: (M, p) \to (N, q)$ be a smooth map-germ. Let $m = \dim M$ and $n = \dim N$.
1.  $f$ is a ***submersion*** at $p$ if $m \geq n$ and $f$ is A-equivalent to the standard projection germ $\pi: (\mathbb{R}^m, 0) \to (\mathbb{R}^n, 0)$.
2.  $f$ is an ***immersion*** at $p$ if $m \leq n$ and $f$ is A-equivalent to the standard inclusion germ $\iota: (\mathbb{R}^m, 0) \to (\mathbb{R}^n, 0)$.

*Intuition: Instead of defining these concepts with derivatives, we define them by their "shape." A submersion is any map that, after a suitable change of coordinates, looks exactly like a projection. An immersion is any map that looks like a clean, non-self-intersecting inclusion of a lower-dimensional space into a higher-dimensional one.*

**Theorem (Equivalence to Classical Definitions).**

Let $f: M \to N$ be a smooth map between manifolds with $f(p) = q$, and let $df_p: T_pM \to T_qN$ be its differential at $p$.
1.  The map-germ of $f$ at $p$ is a submersion if and only if its differential $df_p$ is surjective.
2.  The map-germ of $f$ at $p$ is an immersion if and only if its differential $df_p$ is injective.

*Proof.*
This proof establishes the crucial link between the geometric definition (A-equivalence) and the analytic definition (rank of the differential). The core argument relies on the Inverse Function Theorem.

**(A-Equivalence $\implies$ Rank Condition)**
If $f$ is a submersion, then $\psi \circ f \circ \phi^{-1} = \pi$ for some local diffeomorphisms $\phi, \psi$. The chain rule gives $d\psi_q \circ df_p \circ d(\phi^{-1})_p = d\pi_0$. As $d\psi$ and $d\phi$ are isomorphisms and $d\pi_0$ is surjective, $df_p$ must be surjective. An identical argument holds for immersions, using the injectivity of $d\iota_0$.

**(Rank Condition $\implies$ A-Equivalence)**
This direction constructs the coordinate changes using the Inverse Function Theorem. We prove it for submersions; the proof for immersions is analogous. Assume $df_p$ is surjective. In local coordinates, let $f: \mathbb{R}^m \to \mathbb{R}^n$ with $p=0, q=0$. The $n \times m$ Jacobian matrix of $f$ at $0$ has rank $n$. After reordering coordinates in $\mathbb{R}^m$, we can assume the first $n$ columns are linearly independent. Define a new map $F: \mathbb{R}^m \to \mathbb{R}^m$ by
$$
F(x) = (f_1(x), \dots, f_n(x), x_{n+1}, \dots, x_m).
$$
The Jacobian of $F$ at $0$ is invertible, so by the Inverse Function Theorem, $F$ is a local diffeomorphism. Let $\phi = F^{-1}$ be the desired source coordinate change. In the new coordinates $u=F(x)$, the map $f$ becomes $f \circ \phi(u) = f \circ F^{-1}(u)$. By construction of $F$, the first $n$ components of $u$ are exactly $f_1(x), \dots, f_n(x)$. So, $f(x)$ is just the first $n$ components of $u$. Therefore,
$$
f \circ \phi(u) = (u_1, \dots, u_n) = \pi(u).
$$
Taking $\psi = \operatorname{id}$, we have $\psi \circ f \circ \phi = \pi$, so $f$ is A-equivalent to the projection.
$\square$

**Definition (Constant Rank Map-Germ).**

A smooth map-germ $f: (M, p) \to (N, q)$ has ***constant rank r*** if it is A-equivalent to the standard rank-r map $\rho_r: (\mathbb{R}^m, 0) \to (\mathbb{R}^n, 0)$.

**Theorem (Constant Rank Theorem).**

A smooth map-germ $f: (M, p) \to (N, q)$ has constant rank $r$ in the sense of A-equivalence if and only if there is a neighborhood $U$ of $p$ such that the rank of the differential $df_x$ is equal to $r$ for all $x \in U$.

*Proof.*
**(A-Equivalence $\implies$ Constant Rank of Differential)**
If $f$ is A-equivalent to $\rho_r$, there exist local diffeomorphisms $\phi, \psi$ such that $\psi \circ f \circ \phi^{-1} = \rho_r$ on some neighborhood. By the chain rule, $d\psi \circ df_x \circ d(\phi^{-1}) = d(\rho_r)$. Since $d\psi$ and $d\phi$ are isomorphisms, they preserve the rank. The rank of $d(\rho_r)$ is constant and equal to $r$ everywhere. Therefore, the rank of $df_x$ must be constant and equal to $r$ in the neighborhood where the diffeomorphisms are defined.

**(Constant Rank of Differential $\implies$ A-Equivalence)**
This is the constructive part of the theorem. Assume $\operatorname{rank}(df_x) = r$ for all $x$ in a neighborhood of $p$. We work in local coordinates where $f: \mathbb{R}^m \to \mathbb{R}^n$, with $p=0, q=0$.
1.  **Construct the source diffeomorphism $\phi$:** Since $\operatorname{rank}(df_0)=r$, we can reorder coordinates such that the top-left $r \times r$ submatrix of the Jacobian $J_f(0)$ is invertible. Define a map $F: \mathbb{R}^m \to \mathbb{R}^m$ by
    $$
    F(x_1, \dots, x_m) = (f_1(x), \dots, f_r(x), x_{r+1}, \dots, x_m).
    $$
    The Jacobian of $F$ at $0$ is invertible, so by the Inverse Function Theorem, $F$ is a local diffeomorphism near $0$. Let $\phi = F$. We will work in the new source coordinates $u = F(x)$. The map becomes $g = f \circ F^{-1}$.
2.  **Analyze the simplified map $g$:** Let $u = (u_1, \dots, u_m)$. By construction of $F$, the first $r$ components of $u$ are $(f_1(x), \dots, f_r(x))$. Thus, $g(u) = f(F^{-1}(u))$ has its first $r$ components as $(u_1, \dots, u_r)$. So $g(u)$ has the form
    $$
    g(u_1, \dots, u_m) = (u_1, \dots, u_r, h_{r+1}(u), \dots, h_n(u))
    $$
    for some functions $h_j$.
3.  **Use the rank condition:** The Jacobian of $g$ has the form
    $$
    J_g(u) = \begin{pmatrix} I_r & 0 \\ \frac{\partial h}{\partial u'} & \frac{\partial h}{\partial u''} \end{pmatrix}
    $$
    where $u'=(u_1, \dots, u_r)$ and $u''=(u_{r+1}, \dots, u_m)$. Since $\operatorname{rank}(dg_u) = \operatorname{rank}(df_{F^{-1}(u)}) = r$ everywhere locally, the bottom-right block must be zero, i.e., $\frac{\partial h}{\partial u''} = 0$. This implies that the functions $h_j$ depend only on $u_1, \dots, u_r$. So, $g$ has the form
    $$
    g(u_1, \dots, u_m) = (u_1, \dots, u_r, h_{r+1}(u_1, \dots, u_r), \dots, h_n(u_1, \dots, u_r)).
    $$
4.  **Construct the target diffeomorphism $\psi$:** We define a map to "straighten" the target space. Let $\Psi: \mathbb{R}^n \to \mathbb{R}^n$ be defined by
    $$
    \Psi(v_1, \dots, v_n) = (v_1, \dots, v_r, v_{r+1} - h_{r+1}(v_1, \dots, v_r), \dots, v_n - h_n(v_1, \dots, v_r)).
    $$
    The Jacobian of $\Psi$ is lower triangular with 1s on the diagonal, so it is invertible. By the Inverse Function Theorem, $\Psi$ is a local diffeomorphism. Let $\psi=\Psi$.
5.  **Final Composition:** We compute $\psi \circ g(u) = \Psi(g(u))$. This gives
    $$
    \Psi(u_1, \dots, u_r, h_{r+1}(u'), \dots, h_n(u')) = (u_1, \dots, u_r, h_{r+1}(u') - h_{r+1}(u'), \dots, h_n(u') - h_n(u'))
    $$
    which simplifies to
    $$
    (u_1, \dots, u_r, 0, \dots, 0) = \rho_r(u).
    $$
    We have found $\psi$ and $\phi$ such that $\psi \circ f \circ \phi^{-1} = \rho_r$. Thus, $f$ is A-equivalent to the standard rank-r map.
$\square$

**Theorem (Coordinate Subspaces as Submanifolds).**

Any affine subspace of $\mathbb{R}^n$ is a submanifold of $\mathbb{R}^n$. For instance, the $k$-dimensional subspace $S = \{ (x_1, \dots, x_k, c_{k+1}, \dots, c_n) \in \mathbb{R}^n \}$ for constants $c_i$ is a submanifold.

*Proof.*
A subset $S \subset N$ is a submanifold if, for every point $p \in S$, there is a coordinate chart $(U, \mathbf{x})$ on the ambient manifold $N$ around $p$ such that $\mathbf{x}(U \cap S)$ is a "flat slice" of the coordinate space $\mathbb{R}^n$. For $N=\mathbb{R}^n$ and $S$ an affine subspace, the identity chart $(\mathbb{R}^n, \operatorname{id})$ trivially satisfies this condition for all points in $S$, as $S$ is already a flat slice in its own coordinate space.
$\square$

**Theorem (A-Equivalence and Local Submanifold Structure).**

Let $S \subset N$ be a subset and $q \in S$. Let $\psi: (N, q) \to (N, q)$ be a diffeomorphism-germ. Then $S$ is a submanifold-germ at $q$ if and only if the image $\psi(S)$ is a submanifold-germ at $\psi(q)=q$.

*Proof.*
Diffeomorphisms are smooth, invertible maps with smooth inverses, so they preserve all local geometric properties. Suppose $S$ is a submanifold at $q$. This means there exists a local chart $(U, \mathbf{x})$ on $N$ around $q$ that "straightens out" $S$ into a flat coordinate subspace. We can construct a new chart for $N$ around $q$, $\mathbf{y} = \mathbf{x} \circ \psi^{-1}$. This new chart is well-defined because it is a composition of a diffeomorphism and a chart map. This chart straightens out the transformed set $\psi(S)$, since $\mathbf{y}(\psi(S)) = (\mathbf{x} \circ \psi^{-1})(\psi(S)) = \mathbf{x}(S)$, which is a flat coordinate subspace. The converse follows by applying the same logic to the inverse diffeomorphism $\psi^{-1}$.
$\square$

**Theorem (Regular Value Theorem).**

Let $f: M \to N$ be a smooth map and let $y \in N$ be a regular value of $f$. The preimage $f^{-1}(y)$ is a properly embedded submanifold of $M$ with dimension $\dim M - \dim N$.

*Proof.*
Let $x$ be any point in the preimage $f^{-1}(y)$.
1.  By definition, $y$ being a regular value means that for every $x \in f^{-1}(y)$, the differential $df_x$ is surjective.
2.  From our Equivalence Theorem, a surjective differential $df_x$ is equivalent to the map-germ of $f$ at $x$ being a submersion.
3.  By the definition of a submersion, this means $f$ is locally A-equivalent to the standard projection $\pi$. That is, there exist local diffeomorphisms $\phi_x$ near $x$ and $\psi_x$ near $y$ such that $\psi_x \circ f \circ \phi_x^{-1} = \pi$.
4.  The preimage of a point under the projection $\pi$ is a coordinate subspace, which is a submanifold.
5.  The original preimage, $f^{-1}(y)$, is related to this simple coordinate subspace by local diffeomorphisms. Since diffeomorphisms preserve the property of being a submanifold, $f^{-1}(y)$ must be a submanifold locally at each point $x$.
6.  This argument holds for every point $x \in f^{-1}(y)$. The collection of these local submanifold charts forms an atlas for $f^{-1}(y)$, proving it is a submanifold of dimension $\dim M - \dim N$.
$\square$