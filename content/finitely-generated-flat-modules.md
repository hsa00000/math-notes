---
title: Finitely Generated Flat Modules over a Local Noetherian Ring are Free
description: A collection of theorems establishing that finitely generated flat modules over a local Noetherian ring are free, building from fundamental properties of localization and projectivity.
---

**Theorem 1 (Finitely Generated Modules over a Noetherian Ring are Finitely Presented).**

Let $R$ be a Noetherian ring and $M$ be a finitely generated $R$-module. Then $M$ is finitely presented.

*Proof.*
Since $M$ is finitely generated, there exists a surjective $R$-module homomorphism $\phi: R^n \to M$ for some integer $n \ge 0$. Let $K = \ker(\phi)$. The module $R^n$ is Noetherian because $R$ is. As a submodule of a Noetherian module, $K$ is finitely generated. Thus, there exists a surjective homomorphism $\psi: R^m \to K$ for some integer $m \ge 0$. Composing the inclusion $i: K \to R^n$ with $\psi$ gives a map $R^m \to R^n$ whose image is $K$. This yields the finite presentation of $M$:

$$
R^m \to R^n \to M \to 0
$$

$\square$

**Theorem 2 (Finitely Generated Projective is Finitely Presented).**

Let $R$ be a ring. If an $R$-module $P$ is finitely generated and projective, then $P$ is finitely presented.

*Proof.*
Since $P$ is finitely generated, there exists a surjective homomorphism $\phi: R^n \to P$. Let $K = \ker(\phi)$. The short exact sequence $0 \to K \to R^n \xrightarrow{\phi} P \to 0$ splits because $P$ is projective. Therefore, $R^n \cong P \oplus K$. As a direct summand of a finitely generated module, $K$ is finitely generated. Thus there exists a surjection $\psi: R^m \to K$. This gives a finite presentation $R^m \xrightarrow{i \circ \psi} R^n \to P \to 0$, where $i: K \hookrightarrow R^n$ is the inclusion. $\square$


---


**Theorem 3 (Localization of a Flat Module is Flat).**

Let $R$ be a commutative ring, $M$ an $R$-module, and $S$ a multiplicative subset of $R$. If $M$ is a flat $R$-module, then the localization $S^{-1}M$ is a flat $S^{-1}R$-module.

*Proof.*
Let $0 \to N' \to N \to N'' \to 0$ be an exact sequence of $S^{-1}R$-modules. Viewing this as a sequence of $R$-modules, tensoring with the flat $R$-module $M$ yields the exact sequence $0 \to N' \otimes_R M \to N \otimes_R M \to N'' \otimes_R M \to 0$. Applying the exact functor $S^{-1}(-)$ and using the canonical isomorphism $S^{-1}(X \otimes_R Y) \cong S^{-1}X \otimes_{S^{-1}R} S^{-1}Y$ gives the exact sequence:

$$
0 \to S^{-1}(N') \otimes_{S^{-1}R} S^{-1}M \to S^{-1}(N) \otimes_{S^{-1}R} S^{-1}M \to S^{-1}(N'') \otimes_{S^{-1}R} S^{-1}M \to 0
$$

Since each $N_i$ is an $S^{-1}R$-module, $S^{-1}N_i \cong N_i$. The sequence is $0 \to N' \otimes_{S^{-1}R} S^{-1}M \to N \otimes_{S^{-1}R} S^{-1}M \to N'' \otimes_{S^{-1}R} S^{-1}M \to 0$, which is the tensor product of the original sequence with $S^{-1}M$ over $S^{-1}R$. Its exactness implies $S^{-1}M$ is a flat $S^{-1}R$-module. $\square$

**Theorem 4 (Localization of a Finitely Presented Module is Finitely Presented).**

Let $R$ be a commutative ring, $M$ a finitely presented $R$-module, and $S$ a multiplicative subset of $R$. The localization $S^{-1}M$ is a finitely presented $S^{-1}R$-module.

*Proof.*
Since $M$ is finitely presented, there exists an exact sequence $R^m \to R^n \to M \to 0$. The localization functor $S^{-1}(-)$ is exact, so applying it yields the exact sequence $(S^{-1}R)^m \to (S^{-1}R)^n \to S^{-1}M \to 0$. This is a finite presentation for $S^{-1}M$ over the ring $S^{-1}R$. $\square$

**Theorem 5 (Hom Commutes with Localization for Finitely Presented Modules).**

Let $R$ be a commutative ring, $M$ a finitely presented $R$-module, $N$ an $R$-module, and $\mathfrak{p}$ a prime ideal of $R$. There is a canonical isomorphism of $R_\mathfrak{p}$-modules:

$$
(\operatorname{Hom}_R(M, N))_\mathfrak{p} \cong \operatorname{Hom}_{R_\mathfrak{p}}(M_\mathfrak{p}, N_\mathfrak{p})
$$

*Proof.*
A finite presentation $R^m \xrightarrow{f} R^n \to M \to 0$ gives rise to two exact sequences. First, applying the left-exact functor $\operatorname{Hom}_R(-, N)$ and then localizing at $\mathfrak{p}$ yields the exact sequence $0 \to (\operatorname{Hom}_R(M, N))_\mathfrak{p} \to (N_\mathfrak{p})^n \to (N_\mathfrak{p})^m$. Second, localizing the presentation first and then applying $\operatorname{Hom}_{R_\mathfrak{p}}(-, N_\mathfrak{p})$ yields the exact sequence $0 \to \operatorname{Hom}_{R_\mathfrak{p}}(M_\mathfrak{p}, N_\mathfrak{p}) \to (N_\mathfrak{p})^n \to (N_\mathfrak{p})^m$. The two modules $(\operatorname{Hom}_R(M, N))_\mathfrak{p}$ and $\operatorname{Hom}_{R_\mathfrak{p}}(M_\mathfrak{p}, N_\mathfrak{p})$ are the kernels of the same homomorphism $(N_\mathfrak{p})^n \to (N_\mathfrak{p})^m$ and are thus canonically isomorphic. $\square$


---


**Theorem 6 (Finitely Presented Flat Modules over a Local Ring are Free).**

Let $(R, \mathfrak{m})$ be a local ring and let $M$ be a finitely presented flat $R$-module. Then $M$ is a free $R$-module of finite rank.

*Proof.*
Let $k = R/\mathfrak{m}$ be the residue field. Let $\{\bar{x}_1, \dots, \bar{x}_n\}$ be a basis for the $k$-vector space $M/\mathfrak{m}M$, and let $x_i \in M$ be lifts. By Nakayama's Lemma, $\{x_1, \dots, x_n\}$ generates $M$. This defines a surjective homomorphism $\phi: R^n \to M$. Let $K = \ker(\phi)$, yielding the short exact sequence $0 \to K \to R^n \to M \to 0$. Since $M$ is finitely presented, $K$ is finitely generated. As $M$ is a flat $R$-module, $\operatorname{Tor}_1^R(M, k) = 0$. The long exact sequence of $\operatorname{Tor}$ implies that the sequence obtained by tensoring with $k$ is also short exact:

$$
0 \to K \otimes_R k \to R^n \otimes_R k \xrightarrow{\bar{\phi}} M \otimes_R k \to 0
$$

This is the sequence $0 \to K/\mathfrak{m}K \to k^n \xrightarrow{\bar{\phi}} M/\mathfrak{m}M \to 0$. By construction, $\bar{\phi}$ is an isomorphism, so $K/\mathfrak{m}K = 0$. Since $K$ is finitely generated over a local ring, Nakayama's Lemma implies $K=0$. Thus, $\phi$ is an isomorphism and $M \cong R^n$. $\square$

**Theorem 7 (Finitely Generated Projective Modules over a Local Ring are Free).**

Let $(R, \mathfrak{m})$ be a local ring and let $M$ be a finitely generated projective $R$-module. Then $M$ is a free $R$-module of finite rank.

*Proof.*
Since $M$ is a finitely generated projective $R$-module, it is finitely presented by Theorem 8. Every projective module is flat. Thus, $M$ is a finitely presented flat module over the local ring $R$. By Theorem 4, $M$ is a free $R$-module of finite rank. $\square$

**Theorem 8 (Finitely Generated Flat Modules over a Local Noetherian Ring are Free).**

Let $(R, \mathfrak{m})$ be a local Noetherian ring and let $M$ be a finitely generated flat $R$-module. Then $M$ is a free $R$-module of finite rank.

*Proof.*
The ring $R$ is Noetherian and the module $M$ is finitely generated. By Theorem 1, $M$ is finitely presented. Thus, $M$ is a finitely presented flat module over the local ring $R$. By Theorem 4, $M$ must be a free $R$-module of finite rank. $\square$


---


**Theorem 9 (Finitely Presented Locally Free Modules are Projective).**

Let $M$ be a finitely presented $R$-module. If $M_\mathfrak{p}$ is a free $R_\mathfrak{p}$-module for every prime ideal $\mathfrak{p}$ of $R$, then $M$ is a projective $R$-module.

*Proof.*
An $R$-module is projective if and only if $\operatorname{Hom}_R(M, -)$ is an exact functor. This is equivalent to showing that for any surjection $\pi: F \to M$, the induced map $\operatorname{Hom}_R(M, \pi): \operatorname{Hom}_R(M, F) \to \operatorname{Hom}_R(M, M)$ is surjective. A homomorphism is surjective if and only if it is surjective upon localization at every prime ideal $\mathfrak{p}$. Since $M$ is finitely presented, Theorem 5 provides a commutative diagram where the vertical maps are isomorphisms:

$$
\begin{CD}
(\operatorname{Hom}_R(M, F))_\mathfrak{p} @>>> (\operatorname{Hom}_R(M, M))_\mathfrak{p} \\
@V{\cong}VV @VV{\cong}V \\
\operatorname{Hom}_{R_\mathfrak{p}}(M_\mathfrak{p}, F_\mathfrak{p}) @>>> \operatorname{Hom}_{R_\mathfrak{p}}(M_\mathfrak{p}, M_\mathfrak{p})
\end{CD}
$$

The bottom map is induced by the surjection $\pi_\mathfrak{p}: F_\mathfrak{p} \to M_\mathfrak{p}$. By hypothesis, $M_\mathfrak{p}$ is a free $R_\mathfrak{p}$-module, hence projective. The projectivity of $M_\mathfrak{p}$ ensures the bottom map is surjective for every $\mathfrak{p}$. Consequently, the top map is surjective for every $\mathfrak{p}$, which implies the original map $\operatorname{Hom}_R(M, \pi)$ is surjective. Thus $M$ is projective. $\square$

**Theorem 10 (Finitely Presented Flat Modules are Projective).**

Let $R$ be a commutative ring. If $M$ is a finitely presented flat $R$-module, then $M$ is a projective $R$-module.

*Proof.*
Let $M$ be a finitely presented flat $R$-module. For any prime ideal $\mathfrak{p} \subset R$, the ring $R_\mathfrak{p}$ is a local ring. By Theorem 2, the localization $M_\mathfrak{p}$ is a flat $R_\mathfrak{p}$-module. By Theorem 3, $M_\mathfrak{p}$ is a finitely presented $R_\mathfrak{p}$-module. By Theorem 4, any finitely presented flat module over a local ring is free. Thus, $M_\mathfrak{p}$ is a free $R_\mathfrak{p}$-module for every prime ideal $\mathfrak{p}$. The module $M$ is finitely presented and locally free. By Theorem 6, $M$ is projective. $\square$