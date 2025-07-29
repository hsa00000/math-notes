---
title: Finitely Presented Flat Modules are Projective
description: A proof that a finitely presented flat module over an arbitrary ring is projective.
---

**Theorem.**

Let $R$ be a commutative ring. A finitely presented flat $R$-module $M$ is projective.

_Proof._
An $R$-module $P$ is projective if and only if $\operatorname{Ext}_R^1(P, N) = 0$ for all $R$-modules $N$. Let $D(N) = \operatorname{Hom}_{\mathbb{Z}}(N, \mathbb{Q}/\mathbb{Z})$ denote the character module of an $R$-module $N$. The group $\mathbb{Q}/\mathbb{Z}$ is an injective cogenerator for the category of abelian groups. Consequently, an abelian group $G$ is zero if and only if its dual $D(G) = \operatorname{Hom}_{\mathbb{Z}}(G, \mathbb{Q}/\mathbb{Z})$ is zero. Thus, $\operatorname{Ext}_R^1(M, N) = 0$ for all $N$ if and only if $D(\operatorname{Ext}_R^1(M, N)) = 0$ for all $N$.

For any $R$-module $M$ and any integer $n \ge 0$, there is a natural homomorphism

$$
\tau_n: \operatorname{Tor}_n^R(M, D(N)) \longrightarrow D(\operatorname{Ext}_R^n(M, N)) .
$$

A fundamental result [^1] in homological algebra states that if $M$ is a finitely presented $R$-module, then this map $\tau_n$ is an isomorphism for all $n \ge 0$. For $n=1$, we have the isomorphism:

$$
\operatorname{Tor}_1^R(M, D(N)) \cong D(\operatorname{Ext}_R^1(M, N)) .
$$

We are given that $M$ is a flat module. By definition, an $R$-module $F$ is flat if and only if the functor $-\otimes_R F$ is exact, which is equivalent to $\operatorname{Tor}_n^R(A, F) = 0$ for all $n \ge 1$ and for all $R$-modules $A$. As $\operatorname{Tor}$ is balanced, this is also equivalent to $\operatorname{Tor}_n^R(F, A) = 0$ for all $n \ge 1$ and all $A$.

In particular, for $n=1$, the flatness of $M$ implies $\operatorname{Tor}_1^R(M, A) = 0$ for any $R$-module $A$. Choosing $A = D(N)$, we have

$$
\operatorname{Tor}_1^R(M, D(N)) = 0 .
$$

Using the isomorphism, we conclude that

$$
D(\operatorname{Ext}_R^1(M, N)) = 0 .
$$

As reasoned above, this implies that $\operatorname{Ext}_R^1(M, N) = 0$ for all $R$-modules $N$. Therefore, $M$ is projective. $\square$

[^1]: [[tor-ext-duality-for-finitely-presented-modules]]