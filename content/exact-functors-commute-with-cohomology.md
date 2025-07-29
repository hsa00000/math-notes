<!-- exact-functors-commute-with-cohomology.md -->
---
title: Exact Functors Commute with (Co)homology
description: An exact functor preserves the (co)homology of a (co)chain complex.
---

**Theorem.**

Let $\mathcal{A}$ and $\mathcal{B}$ be abelian categories.

1.  If $F : \mathcal{A} \to \mathcal{B}$ is an exact covariant functor and $C_\bullet$ is a chain complex in $\mathcal{A}$, then there is a natural isomorphism for each $i \in \mathbb{Z}$:
    $$
    F(H_i(C_\bullet)) \cong H_i(F(C_\bullet)).
    $$

2.  If $G : \mathcal{A} \to \mathcal{B}$ is an exact contravariant functor and $C_\bullet$ is a chain complex in $\mathcal{A}$, then there is a natural isomorphism for each $i \in \mathbb{Z}$:
    $$
    G(H_i(C_\bullet)) \cong H^i(G(C_\bullet)).
    $$

*Proof.*
We prove the covariant case; the contravariant case is analogous. An exact functor preserves kernels, images, and quotients. Let the chain complex be $C_\bullet$ with differentials $d_i$. The properties of an exact functor yield the following unbroken chain of natural isomorphisms.

$$
\begin{align*}
F(H_i(C_\bullet)) &= F\big(\ker(d_i) / \operatorname{im}(d_{i+1})\big) \\
&\cong F(\ker(d_i)) / F(\operatorname{im}(d_{i+1})) \\
&\cong \ker(F(d_i)) / \operatorname{im}(F(d_{i+1})) \\
&= H_i(F(C_\bullet))
\end{align*}
$$

The first and last equalities hold by the definition of homology. The first isomorphism holds because $F$ preserves quotients, and the second holds because $F$ preserves kernels and images.
$\square$