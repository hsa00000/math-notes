---
title: Tensor Products of Z-Modules II (Tensor Product of Two Fields over the Integers)
description: An analysis of the structure of the ring for fields L and K over Z. The result depends on the characteristics of the fields and can be the zero ring, a field, a product of fields, or a ring with nilpotent elements.
date: 2025-09-04T12:01:00+08:00
---

**Case 1: Fields with Different Characteristics.**

**Theorem (Different Characteristics).**
Let $L$ and $K$ be fields. If $\operatorname{char}(L) \neq \operatorname{char}(K)$, then $L \otimes_{\mathbb{Z}} K \cong \{0\}$.

_Proof._
Let $\operatorname{char}(L) = p > 0$ and $\operatorname{char}(K) = q$, where $q=0$ or $q$ is a prime distinct from $p$. For any simple tensor $l \otimes k \in L \otimes_{\mathbb{Z}} K$, we have $p \cdot (l \otimes k) = (pl) \otimes k = 0 \otimes k = 0$.

If $q=0$, then $K$ is a field of characteristic zero, so $p$ is an invertible element in $K$. Any $k \in K$ can be written as $k = p \cdot (k/p)$.

$$
l \otimes k = l \otimes (p \cdot (k/p)) = (p \cdot l) \otimes (k/p) = 0 \otimes (k/p) = 0
$$

If $q > 0$ and $q \neq p$, then $p$ and $q$ are distinct primes, so $\operatorname{gcd}(p, q) = 1$. By the Bézout identity, there exist integers $a, b$ such that $ap + bq = 1$. For any simple tensor $x = l \otimes k$, we have $p \cdot x = (pl) \otimes k = 0$ and $q \cdot x = l \otimes (qk) = 0$.

$$
x = 1 \cdot x = (ap + bq) \cdot x = a(p \cdot x) + b(q \cdot x) = a \cdot 0 + b \cdot 0 = 0
$$

Since every simple tensor is zero and these elements generate the module, $L \otimes_{\mathbb{Z}} K \cong \{0\}$.
$\square$

**Case 2: Fields with the Same Characteristic.**

**Theorem (Same Characteristic).**
Let $L$ and $K$ be fields with the same characteristic. Let $F$ be their common prime subfield ($F=\mathbb{Q}$ if characteristic is 0, $F=\mathbb{F}_p$ if characteristic is $p$). There is a ring isomorphism:

$$
L \otimes_{\mathbb{Z}} K \cong L \otimes_F K
$$

_Proof._

The fields $L$ and $K$ are $F$-algebras, so the tensor product $L \otimes_F K$ is a well-defined $F$-algebra.

Consider the canonical map $\phi: L \times K \to L \otimes_F K$ given by $\phi(l, k) = l \otimes k$. This map is $F$-bilinear by definition, and therefore also $\mathbb{Z}$-bilinear since the action of any $n \in \mathbb{Z}$ is a special case of the action of $F$. By the universal property of the tensor product over $\mathbb{Z}$, $\phi$ induces a unique $\mathbb{Z}$-module homomorphism $\Phi: L \otimes_{\mathbb{Z}} K \to L \otimes_F K$ such that $\Phi(l \otimes k) = l \otimes k$ for all $l \in L, k \in K$.

Conversely, consider the map $\psi: L \times K \to L \otimes_{\mathbb{Z}} K$ given by $\psi(l, k) = l \otimes k$. This map is $\mathbb{Z}$-bilinear. We show it is also $F$-bilinear. Let $\alpha \in F$. By symmetry, it suffices to show that for any $l \in L, k \in K$, the relation $(\alpha \cdot l) \otimes k = l \otimes (\alpha \cdot k)$ holds in $L \otimes_{\mathbb{Z}} K$.

Case 1: The characteristic is $p > 0$. Then $F = \mathbb{F}_p$, and any $\alpha \in F$ can be represented by an integer $n$ where $0 \le n < p$. The action is $\alpha \cdot l = n \cdot l$. Then $(\alpha \cdot l) \otimes k = (n \cdot l) \otimes k = n(l \otimes k) = l \otimes (n \cdot k) = l \otimes (\alpha \cdot k)$.

Case 2: The characteristic is 0. Then $F = \mathbb{Q}$, and any $\alpha \in F$ can be written as $n/m$ for $n, m \in \mathbb{Z}$ with $m \neq 0$. For any integer $n$, $(n \cdot l) \otimes k = n(l \otimes k) = l \otimes (n \cdot k)$. For the reciprocal $1/m$, we have $m \cdot ((1/m \cdot l) \otimes k) = (m \cdot (1/m \cdot l)) \otimes k = l \otimes k$. Similarly, $m \cdot (l \otimes (1/m \cdot k)) = l \otimes (m \cdot (1/m \cdot k)) = l \otimes k$. Since $L$ and $K$ are $\mathbb{Q}$-vector spaces, they are divisible $\mathbb{Z}$-modules, which makes $L \otimes_{\mathbb{Z}} K$ a divisible $\mathbb{Z}$-module. Thus, multiplication by a non-zero integer $m$ is an automorphism. It follows that $(1/m \cdot l) \otimes k = l \otimes (1/m \cdot k)$. Combining these results gives $((n/m) \cdot l) \otimes k = n((1/m \cdot l) \otimes k) = n(l \otimes (1/m \cdot k)) = l \otimes (n(1/m \cdot k)) = l \otimes ((n/m) \cdot k)$.

In both cases, $\psi$ is $F$-bilinear. By the universal property of the tensor product over $F$, $\psi$ induces a unique $F$-module homomorphism $\Psi: L \otimes_F K \to L \otimes_{\mathbb{Z}} K$ such that $\Psi(l \otimes k) = l \otimes k$.

The maps $\Phi$ and $\Psi$ are mutually inverse, since $(\Psi \circ \Phi)(l \otimes k) = \Psi(l \otimes k) = l \otimes k$ and $(\Phi \circ \Psi)(l \otimes k) = \Phi(l \otimes k) = l \otimes k$. As these compositions are the identity on the generating simple tensors, they are the identity maps on the respective modules. Thus, $\Phi$ is an isomorphism of abelian groups.

Finally, $\Phi$ is a ring homomorphism:

$$
\Phi((l_1 \otimes k_1)(l_2 \otimes k_2)) = \Phi((l_1 l_2) \otimes (k_1 k_2)) = (l_1 l_2) \otimes (k_1 k_2) = (l_1 \otimes k_1)(l_2 \otimes k_2) = \Phi(l_1 \otimes k_1)\Phi(l_2 \otimes k_2)
$$

Therefore, $\Phi$ is a ring isomorphism. $\square$

The structure of $L \otimes_F K$ is determined by the behavior of one field extension over the other. Assume $L/F$ is a finite extension. By the Primitive Element Theorem, $L \cong F[x]/(f(x))$ for some irreducible polynomial $f(x) \in F[x]$. This gives the isomorphism:

$$
L \otimes_F K \cong (F[x]/(f(x))) \otimes_F K \cong K[x]/(f(x))
$$

Let the prime factorization of $f(x)$ in the polynomial ring $K[x]$ be $f(x) = g_1(x)^{e_1} \cdots g_r(x)^{e_r}$. By the Chinese Remainder Theorem:

$$
K[x]/(f(x)) \cong K[x]/(g_1(x)^{e_1}) \times \cdots \times K[x]/(g_r(x)^{e_r})
$$

**Subcase: Separable Extensions.**

If $L/F$ is a separable extension, then $f(x)$ is a separable polynomial, which implies all exponents in its factorization over $K$ are $e_i=1$. Each factor $K[x]/(g_i(x))$ is a field, as each $g_i(x)$ is irreducible over $K$. Thus, for separable extensions, $L \otimes_F K$ is a direct product of fields. It is a field if and only if $f(x)$ remains irreducible over $K$ (i.e., $r=1$).

**Example (Tensor product is a field).**
Consider $\mathbb{Q}(\sqrt{2}) \otimes_{\mathbb{Z}} \mathbb{Q}(\sqrt{3})$. The common prime subfield is $F=\mathbb{Q}$. Let $L = \mathbb{Q}(\sqrt{2}) \cong \mathbb{Q}[x]/(x^2-2)$ and $K = \mathbb{Q}(\sqrt{3})$. The tensor product is isomorphic to $\mathbb{Q}(\sqrt{3})[x]/(x^2-2)$. The polynomial $x^2-2$ is irreducible over $\mathbb{Q}(\sqrt{3})$, so the resulting ring is a field, which is the compositum $\mathbb{Q}(\sqrt{2}, \sqrt{3})$.

**Example (Tensor product is a product of fields).**
Consider $\mathbb{C} \otimes_{\mathbb{Z}} \mathbb{C}$. This is isomorphic to $\mathbb{C} \otimes_{\mathbb{Q}} \mathbb{C}$. It is easier to view this as $\mathbb{C} \otimes_{\mathbb{R}} \mathbb{C}$ since both are $\mathbb{R}$-algebras. Let $L = \mathbb{C} \cong \mathbb{R}[x]/(x^2+1)$ and $K = \mathbb{C}$. The tensor product is isomorphic to $\mathbb{C}[x]/(x^2+1)$. Over $\mathbb{C}$, the polynomial factors as $x^2+1 = (x-i)(x+i)$. By the Chinese Remainder Theorem:

$$
\mathbb{C}[x]/(x^2+1) \cong \mathbb{C}[x]/(x-i) \times \mathbb{C}[x]/(x+i) \cong \mathbb{C} \times \mathbb{C}
$$

This ring is not a field as it contains zero divisors, e.g., $(1,0) \cdot (0,1) = (0,0)$.

**Subcase: Inseparable Extensions.**

This case occurs only when $\operatorname{char}(F) = p > 0$. If $L/F$ is an inseparable extension, the polynomial $f(x)$ is not separable, and at least one exponent $e_i$ in its factorization over $K$ will be greater than 1. The ring $K[x]/(g_i(x)^{e_i})$ is not a field and contains non-zero nilpotent elements. For instance, the element represented by the class of $g_i(x)$ is non-zero, but its $e_i$-th power is zero.

**Example (Tensor product with nilpotents).**
Let $F = \mathbb{F}_p(t)$ be the field of rational functions in $t$ over $\mathbb{F}_p$. Let $L = F(t^{1/p})$. This is an inseparable extension, as $L \cong F[x]/(x^p - t)$. Consider the tensor product $L \otimes_F L$.

$$
L \otimes_F L \cong L[x]/(x^p - t)
$$

In the field $L$, the element $t$ has a $p$-th root, namely $t^{1/p}$. The polynomial factors completely over $L$:

$$
x^p - t = x^p - (t^{1/p})^p = (x - t^{1/p})^p
$$

Therefore, $L \otimes_F L \cong L[x]/((x - t^{1/p})^p)$. Let $y = x - t^{1/p}$. The ring is isomorphic to $L[y]/(y^p)$. In this ring, the element represented by $y$ is non-zero, but $y^p = 0$, so it is a non-zero nilpotent element.
