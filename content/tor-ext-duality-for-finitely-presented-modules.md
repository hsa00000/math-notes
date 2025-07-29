---
title: Tor-Ext Duality for Finitely Presented Modules
description: Proof of the natural isomorphism between the first Tor group and the dual of the first Ext group when the first argument is a finitely presented module.
---

**Theorem.**

Let $R$ be a ring, $M$ be a finitely presented left $R$-module, and $N$ be a left $R$-module. Let $D(N) = \operatorname{Hom}_{\mathbb{Z}}(N, \mathbb{Q}/\mathbb{Z})$ be the character module of $N$. There is a natural isomorphism:

$$
\operatorname{Tor}_1^R(M, D(N)) \cong D(\operatorname{Ext}_R^1(M, N))
$$

**Proof.**

*Proof.*
Since $M$ is a finitely presented left $R$-module, there exists a free presentation, which is an exact sequence of the form:

$$
F_1 \xrightarrow{d_1} F_0 \xrightarrow{d_0} M \to 0
$$

where $F_1$ and $F_0$ are free left $R$-modules of finite rank.

Applying the functor $\operatorname{Hom}_R(-, N)$ yields a long exact sequence. As $F_0$ is projective, $\operatorname{Ext}_R^1(F_0, N) = 0$, which gives the exact sequence:

$$
\operatorname{Hom}_R(F_0, N) \xrightarrow{d_1^*} \operatorname{Hom}_R(F_1, N) \to \operatorname{Ext}_R^1(M, N) \to 0
$$

The character module functor $D$ is exact. Applying it to the sequence above yields the exact sequence:

$$
0 \to D(\operatorname{Ext}_R^1(M, N)) \to D(\operatorname{Hom}_R(F_1, N)) \xrightarrow{D(d_1^*)} D(\operatorname{Hom}_R(F_0, N))
$$

This identifies $D(\operatorname{Ext}_R^1(M, N))$ with $\ker(D(d_1^*))$.

Applying the functor $- \otimes_R D(N)$ to the free presentation of $M$ yields a long exact sequence. As $F_0$ is flat, $\operatorname{Tor}_1^R(F_0, D(N)) = 0$, which gives the exact sequence:

$$
0 \to \operatorname{Tor}_1^R(M, D(N)) \to F_1 \otimes_R D(N) \xrightarrow{d_1 \otimes 1} F_0 \otimes_R D(N)
$$

This identifies $\operatorname{Tor}_1^R(M, D(N))$ with $\ker(d_1 \otimes 1)$.

For any free $R$-module $F$ of finite rank, there is a natural isomorphism $\eta_F: F \otimes_R D(N) \xrightarrow{\cong} D(\operatorname{Hom}_R(F, N))$. These isomorphisms induce a commutative diagram with exact rows:

$$
\begin{CD}
0 @>>> \operatorname{Tor}_1^R(M, D(N)) @>>> F_1 \otimes_R D(N) @>{d_1 \otimes 1}>> F_0 \otimes_R D(N) \\
@. @VVV @V{\eta_{F_1}}V{\cong}V @V{\eta_{F_0}}V{\cong}V \\
0 @>>> D(\operatorname{Ext}_R^1(M, N)) @>>> D(\operatorname{Hom}_R(F_1, N)) @>{D(d_1^*)}>> D(\operatorname{Hom}_R(F_0, N))
\end{CD}
$$

Five lemma implies that the induced map from $\operatorname{Tor}_1^R(M, D(N))$ to $D(\operatorname{Ext}_R^1(M, N))$ is an isomorphism.
$\square$