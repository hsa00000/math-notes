<!-- finitely-presented-flat-modules-are-projective.md -->
---
title: Finitely Presented Flat Modules are Projective
description: A proof that a finitely presented flat R-module is projective, demonstrated through localization techniques.
---

**Theorem 1.**

Let $R$ be a commutative ring, $M$ a finitely presented $R$-module, and $S$ a multiplicative subset of $R$. The localization $S^{-1}M$ is a finitely presented $S^{-1}R$-module.

*Proof.*
Since $M$ is finitely presented, there exists an exact sequence:
$$
R^m \to R^n \to M \to 0
$$
Since the localization functor $S^{-1}(-)$ is exact, applying it yields an exact sequence:
$$
(S^{-1}R)^m \to (S^{-1}R)^n \to S^{-1}M \to 0
$$
Thus, $S^{-1}M$ is a finitely presented $S^{-1}R$-module.
$\square$

**Theorem 2.**

Let $R$ be a commutative ring, $M$ a flat $R$-module, and $S$ a multiplicative subset of $R$. The localization $S^{-1}M$ is a flat $S^{-1}R$-module.

*Proof.*
Let the following be an exact sequence of $S^{-1}R$-modules:
$$
0 \to N' \to N \to N'' \to 0
$$
Since $M$ is a flat $R$-module, the sequence obtained by tensoring with $M$ over $R$ is exact:
$$
0 \to N' \otimes_R M \to N \otimes_R M \to N'' \otimes_R M \to 0
$$
Applying the exact functor $S^{-1}(-)$ yields another exact sequence:
$$
0 \to S^{-1}(N' \otimes_R M) \to S^{-1}(N \otimes_R M) \to S^{-1}(N'' \otimes_R M) \to 0
$$
There is a canonical isomorphism for any $R$-modules $X, Y$:
$$
S^{-1}(X \otimes_R Y) \cong S^{-1}X \otimes_{S^{-1}R} S^{-1}Y
$$
Since each $N_i$ is an $S^{-1}R$-module, $S^{-1}N_i \cong N_i$. The sequence becomes the following exact sequence:
$$
0 \to N' \otimes_{S^{-1}R} S^{-1}M \to N \otimes_{S^{-1}R} S^{-1}M \to N'' \otimes_{S^{-1}R} S^{-1}M \to 0
$$
Therefore, $S^{-1}M$ is a flat $S^{-1}R$-module.
$\square$

**Theorem 3.**

Let $R$ be a commutative ring, $M$ a finitely presented $R$-module, $N$ an $R$-module, and $\mathfrak{p}$ a prime ideal of $R$. There exists a canonical isomorphism of $R_\mathfrak{p}$-modules:
$$
(\operatorname{Hom}_R(M, N))_\mathfrak{p} \cong \operatorname{Hom}_{R_\mathfrak{p}}(M_\mathfrak{p}, N_\mathfrak{p})
$$

*Proof.*
Since $M$ is finitely presented, there is an exact sequence:
$$
R^m \xrightarrow{f} R^n \xrightarrow{g} M \to 0
$$
Applying the left-exact functor $\operatorname{Hom}_R(-, N)$ gives the exact sequence:
$$
0 \to \operatorname{Hom}_R(M, N) \to N^n \to N^m
$$
Localizing at $\mathfrak{p}$ is exact, so we have:
$$
0 \to (\operatorname{Hom}_R(M, N))_\mathfrak{p} \to (N_\mathfrak{p})^n \to (N_\mathfrak{p})^m
$$
The kernel of the map $(N_\mathfrak{p})^n \to (N_\mathfrak{p})^m$ is $(\operatorname{Hom}_R(M, N))_\mathfrak{p}$.

Alternatively, localizing the presentation of $M$ at $\mathfrak{p}$ gives an exact sequence of $R_\mathfrak{p}$-modules:
$$
R_\mathfrak{p}^m \to R_\mathfrak{p}^n \to M_\mathfrak{p} \to 0
$$
Applying the left-exact functor $\operatorname{Hom}_{R_\mathfrak{p}}(-, N_\mathfrak{p})$ gives the exact sequence:
$$
0 \to \operatorname{Hom}_{R_\mathfrak{p}}(M_\mathfrak{p}, N_\mathfrak{p}) \to (N_\mathfrak{p})^n \to (N_\mathfrak{p})^m
$$
The kernel of the map $(N_\mathfrak{p})^n \to (N_\mathfrak{p})^m$ is $\operatorname{Hom}_{R_\mathfrak{p}}(M_\mathfrak{p}, N_\mathfrak{p})$.

The two kernels are kernels of the same map between the same modules, hence they are canonically isomorphic.
$\square$

**Theorem 4.**

Let $(R, \mathfrak{m})$ be a local ring and let $M$ be a finitely presented flat $R$-module. Then $M$ is a free $R$-module of finite rank.

*Proof.*
Let $k = R/\mathfrak{m}$ be the residue field. The quotient $M/\mathfrak{m}M$ is a finite-dimensional $k$-vector space. Let $\{\bar{x}_1, \dots, \bar{x}_n\}$ be a basis for $M/\mathfrak{m}M$, and let $x_1, \dots, x_n \in M$ be lifts. By Nakayama's Lemma, $\{x_1, \dots, x_n\}$ is a minimal generating set for $M$. This defines a surjective $R$-module homomorphism $\phi: R^n \to M$. Let $K = \ker(\phi)$. The sequence is exact:
$$
0 \to K \to R^n \to M \to 0
$$
Since $M$ is finitely presented over $R$, the kernel $K$ is a finitely generated $R$-module. As $M$ is a flat $R$-module, $\operatorname{Tor}_1^R(M, k) = 0$. Tensoring the short exact sequence with $k$ yields a short exact sequence of $k$-vector spaces:
$$
0 \to K \otimes_R k \to R^n \otimes_R k \xrightarrow{\bar{\phi}} M \otimes_R k \to 0
$$
This sequence is $0 \to K/\mathfrak{m}K \to k^n \xrightarrow{\bar{\phi}} M/\mathfrak{m}M \to 0$. By construction, $\bar{\phi}$ is an isomorphism. This implies $K/\mathfrak{m}K = 0$. Since $K$ is finitely generated over the local ring $R$, Nakayama's Lemma implies $K=0$. Thus, $\phi$ is an isomorphism and $M$ is a free $R$-module of rank $n$.
$\square$

**Theorem 5.**

Let $M$ be a finitely presented $R$-module. If $M_\mathfrak{p}$ is a free $R_\mathfrak{p}$-module for every prime ideal $\mathfrak{p}$ of $R$, then $M$ is a projective $R$-module.

*Proof.*
To show $M$ is projective, we must show that any surjection $\pi: F \to M$ from a free module $F$ splits. This is equivalent to showing that the map $\alpha: \operatorname{Hom}_R(M, F) \to \operatorname{Hom}_R(M, M)$ given by $\alpha(h) = \pi \circ h$ is surjective, as its image would contain $\operatorname{id}_M$.

A homomorphism of $R$-modules is surjective if and only if it is surjective at every localization. We check the map for an arbitrary prime $\mathfrak{p}$:
$$
\alpha_\mathfrak{p}: (\operatorname{Hom}_R(M, F))_\mathfrak{p} \to (\operatorname{Hom}_R(M, M))_\mathfrak{p}
$$
Since $M$ is finitely presented, Theorem 3 provides canonical isomorphisms $(\operatorname{Hom}_R(M, F))_\mathfrak{p} \cong \operatorname{Hom}_{R_\mathfrak{p}}(M_\mathfrak{p}, F_\mathfrak{p})$ and $(\operatorname{Hom}_R(M, M))_\mathfrak{p} \cong \operatorname{Hom}_{R_\mathfrak{p}}(M_\mathfrak{p}, M_\mathfrak{p})$. The localized map is therefore $\alpha_\mathfrak{p}: \operatorname{Hom}_{R_\mathfrak{p}}(M_\mathfrak{p}, F_\mathfrak{p}) \to \operatorname{Hom}_{R_\mathfrak{p}}(M_\mathfrak{p}, M_\mathfrak{p})$.

By hypothesis, $M_\mathfrak{p}$ is a free $R_\mathfrak{p}$-module, hence it is projective over $R_\mathfrak{p}$. The surjection $\pi_\mathfrak{p}: F_\mathfrak{p} \to M_\mathfrak{p}$ must split. This means there exists a section $s_\mathfrak{p}: M_\mathfrak{p} \to F_\mathfrak{p}$ such that $\pi_\mathfrak{p} \circ s_\mathfrak{p} = \operatorname{id}_{M_\mathfrak{p}}$. The existence of such a section implies that $\alpha_\mathfrak{p}$ is surjective.

Since $\alpha_\mathfrak{p}$ is surjective for all primes $\mathfrak{p}$, the map $\alpha$ is surjective. Therefore, there exists $s \in \operatorname{Hom}_R(M, F)$ such that $\pi \circ s = \operatorname{id}_M$. The map $\pi$ splits, and $M$ is projective.
$\square$

**Theorem 6.**

Let $R$ be a commutative ring. If $M$ is a finitely presented flat $R$-module, then $M$ is a projective $R$-module.

*Proof.*
Let $M$ be a finitely presented flat $R$-module. Let $\mathfrak{p}$ be an arbitrary prime ideal of $R$. By Theorem 1 and Theorem 2, the localization $M_\mathfrak{p}$ is a finitely presented flat module over the local ring $R_\mathfrak{p}$. By Theorem 4, any finitely presented flat module over a local ring is free. Thus, $M_\mathfrak{p}$ is a free $R_\mathfrak{p}$-module for every prime ideal $\mathfrak{p}$.

The module $M$ is finitely presented and locally free. By Theorem 5, a finitely presented module that is locally free is projective. Therefore, $M$ is a projective $R$-module.
$\square$