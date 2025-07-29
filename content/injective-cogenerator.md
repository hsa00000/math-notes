---
title: Injective Cogenerator
description: Definition of an injective cogenerator and the proof that every module can be embedded into a product of copies of an injective cogenerator.
---

**Definition.**

Let $R$ be a commutative ring. An $R$-module $C$ is a **_cogenerator_** for the category of $R$-modules if for any nonzero $R$-module $M$ and any nonzero element $m \in M$, there exists an $R$-module homomorphism $f: M \to C$ such that $f(m) \neq 0$. An **_injective cogenerator_** is a module that is both injective and a cogenerator.

**Theorem.**

Let $R$ be a commutative ring. If $I$ is an injective cogenerator for the category of left $R$-modules, then every left $R$-module $M$ can be embedded into a direct product of copies of $I$.

_Proof._

Let $M$ be a left $R$-module and let $I$ be an injective cogenerator. Let the index set be $\mathcal{F} = \operatorname{Hom}_R(M, I)$, the set of all $R$-module homomorphisms from $M$ to $I$.

Consider the direct product $P = \prod_{f \in \mathcal{F}} I_f$, where each $I_f$ is a copy of $I$. As a direct product of injective modules, $P$ is an injective $R$-module.

Define the evaluation homomorphism $\psi: M \to P$ by $\psi(m) = (f(m))_{f \in \mathcal{F}}$. This is an $R$-module homomorphism.

To show $\psi$ is a monomorphism, its kernel must be shown to be trivial. Let $m \in M$ be a nonzero element. Since $I$ is a cogenerator, there exists a homomorphism $g \in \mathcal{F}$ such that $g(m) \neq 0$. The $g$-th component of $\psi(m)$ is $g(m)$, which is nonzero. Therefore, $\psi(m) \neq 0$. This implies that $\operatorname{ker}(\psi) = \{0\}$.

Thus, $\psi$ is a monomorphism from $M$ into the injective module $P$.

$\square$

**Theorem.**

For any ring $R$, the category of left $R$-modules possesses an injective cogenerator.

_Proof._

The proof proceeds in two main steps. First, an injective cogenerator for the category of abelian groups ($\mathbb{Z}$-modules) is established. Second, this is used to construct an injective cogenerator for any category of $R$-modules.

The module $\mathbb{Q}/\mathbb{Z}$ is an injective cogenerator for the category of $\mathbb{Z}$-modules. As a divisible group, it is injective. To show it is a cogenerator, let $A$ be a nonzero abelian group and $a \in A$ be a nonzero element. Consider the cyclic subgroup $\langle a \rangle$. If the order of $a$ is infinite, then $\langle a \rangle \cong \mathbb{Z}$, and the map $f: \langle a \rangle \to \mathbb{Q}/\mathbb{Z}$ defined by $f(ka) = k/2 + \mathbb{Z}$ for $k \in \mathbb{Z}$ is a nonzero homomorphism. If the order of $a$ is a finite integer $n > 1$, then $\langle a \rangle \cong \mathbb{Z}/n\mathbb{Z}$, and the map $f: \langle a \rangle \to \mathbb{Q}/\mathbb{Z}$ defined by $f(ka) = k/n + \mathbb{Z}$ for $k \in \mathbb{Z}$ is a well-defined, nonzero homomorphism. By the injectivity of $\mathbb{Q}/\mathbb{Z}$, this map $f$ extends to a homomorphism $g: A \to \mathbb{Q}/\mathbb{Z}$ such that $g(a) = f(a) \neq 0$.

Let $C$ be an injective cogenerator for $\mathbb{Z}$-modules, such as $C = \mathbb{Q}/\mathbb{Z}$. Let $I = \operatorname{Hom}_{\mathbb{Z}}(R, C)$. The module $I$ is a left $R$-module via the action $(r \cdot \phi)(s) = \phi(sr)$ for $r, s \in R$ and $\phi \in I$.

_Injectivity of $I$_: The functor $\operatorname{Hom}_R(-, I)$ is exact because $\operatorname{Hom}_R(-, \operatorname{Hom}_{\mathbb{Z}}(R, C)) \cong \operatorname{Hom}_{\mathbb{Z}}(- \otimes_R R, C) \cong \operatorname{Hom}_{\mathbb{Z}}(-, C)$, and the latter is an exact functor as $C$ is $\mathbb{Z}$-injective. Therefore, $I$ is an injective left $R$-module.

_Cogenerator Property of $I$_: Let $M$ be a nonzero left $R$-module and $m \in M$ be a nonzero element. There exists a nonzero $\mathbb{Z}$-homomorphism $g: M \to C$. By Hom-tensor adjunction
$$
\operatorname{Hom}_R(M, \operatorname{Hom}_{\mathbb{Z}}(R, C)) \cong \operatorname{Hom}_{\mathbb{Z}}(M \otimes_R R, C)
$$
this corresponds to a nonzero $R$-homomorphism $f: M \to \operatorname{Hom}_{\mathbb{Z}}(R, C) = I$. Thus, $I$ is a cogenerator for left $R$-modules.

$\square$
