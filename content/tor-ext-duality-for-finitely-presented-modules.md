---
title: General Tor-Ext Duality
description: Proof of the natural isomorphism between the i-th Tor group and the dual of the i-th Ext group for a finitely presented module.
---

**Theorem.**

Let $R$ be a ring, $M$ be a finitely presented left $R$-module, and $N$ be a left $R$-module. For any integer $i \ge 0$, let $D(N) = \operatorname{Hom}_{\mathbb{Z}}(N, \mathbb{Q}/\mathbb{Z})$ be the character module of $N$. There is a natural isomorphism:

$$
\operatorname{Tor}_i^R(M, D(N)) \cong D(\operatorname{Ext}_R^i(M, N))
$$

**Proof.**

*Proof.*
Since $M$ is a finitely presented left $R$-module, there exists a resolution of $M$ by finitely generated projective left $R$-modules:

$$
\dots \to P_1 \xrightarrow{d_1} P_0 \xrightarrow{\epsilon} M \to 0
$$

By definition, $\operatorname{Tor}_i^R(M, D(N))$ is the $i$-th homology of the chain complex $P_\bullet \otimes_R D(N)$. Likewise, $\operatorname{Ext}_R^i(M, N)$ is the $i$-th cohomology of the cochain complex $C^\bullet = \operatorname{Hom}_R(P_\bullet, N)$.

For any finitely generated projective $R$-module $P$, there exists a natural isomorphism:

$$
\eta_P: P \otimes_R D(N) \xrightarrow{\cong} D(\operatorname{Hom}_R(P, N))
$$

These isomorphisms for each $P_i$ in the resolution constitute a natural isomorphism of complexes $\eta_\bullet: P_\bullet \otimes_R D(N) \xrightarrow{\cong} D(C^\bullet)$. An isomorphism of complexes induces an isomorphism on homology groups.

The functor $D(-) = \operatorname{Hom}_{\mathbb{Z}}(-, \mathbb{Q}/\mathbb{Z})$ is exact, as $\mathbb{Q}/\mathbb{Z}$ is an injective $\mathbb{Z}$-module. An exact functor commutes with the computation of homology. Therefore, $H_i(D(C^\bullet)) \cong D(H^i(C^\bullet))$.

This yields a chain of natural isomorphisms:

$$
\begin{align*}
\operatorname{Tor}_i^R(M, D(N)) &\cong H_i(P_\bullet \otimes_R D(N)) \\
&\cong H_i(D(\operatorname{Hom}_R(P_\bullet, N))) \\
&\cong D(H^i(\operatorname{Hom}_R(P_\bullet, N))) \\
&\cong D(\operatorname{Ext}_R^i(M, N))
\end{align*}
$$

The result is thus established for all $i \ge 0$.
$\\square$