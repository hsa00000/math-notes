---
title: Tor-Ext Duality
description: The duality relationship between Tor and Ext functors for modules over a commutative ring.
---

**Theorem.**

Let $R$ be a commutative ring, and let $M, N$ be $R$-modules. For any injective cogenerator $E$ of the category of abelian groups (e.g., $E = \mathbb{Q}/\mathbb{Z}$), there is a natural isomorphism for each $i \ge 0$:

$$
\operatorname{Hom}_{\mathbb{Z}}(\operatorname{Tor}^R_i(M, N), E) \cong \operatorname{Ext}^i_R(M, \operatorname{Hom}_{\mathbb{Z}}(N, E)).
$$

Letting $D_E(-) = \operatorname{Hom}_{\mathbb{Z}}(-, E)$, this can be written as $D_E(\operatorname{Tor}^R_i(M, N)) \cong \operatorname{Ext}^i_R(M, D_E(N))$.

*Proof.*
Let $P_\bullet \to M$ be a projective resolution of $M$ over $R$:

$$
\cdots \to P_2 \xrightarrow{d_2} P_1 \xrightarrow{d_1} P_0 \xrightarrow{\varepsilon} M \to 0.
$$

By definition, $\operatorname{Tor}^R_i(M, N)$ is the $i$-th homology of the chain complex $P_\bullet \otimes_R N$:

$$
\operatorname{Tor}^R_i(M, N) = H_i(P_\bullet \otimes_R N).
$$

Apply the functor $D_E(-) = \operatorname{Hom}_{\mathbb{Z}}(-, E)$. Since $E$ is an injective abelian group, $D_E$ is an exact functor. Therefore, it commutes with taking homology, turning homology into cohomology:

$$
\operatorname{Hom}_{\mathbb{Z}}(\operatorname{Tor}^R_i(M, N), E) = \operatorname{Hom}_{\mathbb{Z}}(H_i(P_\bullet \otimes_R N), E) \cong H^i(\operatorname{Hom}_{\mathbb{Z}}(P_\bullet \otimes_R N, E)).
$$

By the Hom-tensor adjunction, we have a natural isomorphism of cochain complexes:

$$
\operatorname{Hom}_{\mathbb{Z}}(P_\bullet \otimes_R N, E) \cong \operatorname{Hom}_R(P_\bullet, \operatorname{Hom}_{\mathbb{Z}}(N, E)).
$$

The cohomology of the complex on the right-hand side is, by definition, the Ext group, since $P_\bullet$ is a projective resolution of $M$:

$$
H^i(\operatorname{Hom}_R(P_\bullet, \operatorname{Hom}_{\mathbb{Z}}(N, E))) = \operatorname{Ext}^i_R(M, \operatorname{Hom}_{\mathbb{Z}}(N, E)).
$$

Combining these isomorphisms yields the desired result:

$$
\operatorname{Hom}_{\mathbb{Z}}(\operatorname{Tor}^R_i(M, N), E) \cong \operatorname{Ext}^i_R(M, \operatorname{Hom}_{\mathbb{Z}}(N, E)).
$$
$\square$