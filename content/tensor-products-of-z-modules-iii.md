---
title: Tensor Products of Z-Modules III (Tensor Product of R-Vector Spaces over Z)
description: Analysis of the structure of V and W over Z where V and W are vector spaces over the real numbers R. The result is a Q-vector space of very large dimension.
date: 2025-09-04
---

**Structure as an Abelian Group.**

Let $V$ and $W$ be vector spaces over the field of real numbers, $\mathbb{R}$. The tensor product $V \otimes_{\mathbb{Z}} W$ is formed by treating $V$ and $W$ only as abelian groups (i.e., $\mathbb{Z}$-modules). The resulting object is, by definition, an abelian group whose elements are finite sums of simple tensors $v \otimes w$ for $v \in V, w \in W$. The relations are those of a $\mathbb{Z}$-module tensor product:
$$
(v_1 + v_2) \otimes w = v_1 \otimes w + v_2 \otimes w
$$
$$
v \otimes (w_1 + w_2) = v \otimes w_1 + v \otimes w_2
$$
$$
(nv) \otimes w = v \otimes (nw) \text{ for any integer } n \in \mathbb{Z}
$$


**Absence of a Natural R-Vector Space Structure.**

There is no natural way to define scalar multiplication by an element $r \in \mathbb{R}$ on a simple tensor $v \otimes w$. A proposed definition such as $r \cdot (v \otimes w) = (rv) \otimes w$ is not well-defined because it must be consistent with $r \cdot (v \otimes w) = v \otimes (rw)$. However, the axioms of the tensor product over $\mathbb{Z}$ do not guarantee that $(rv) \otimes w = v \otimes (rw)$ for $r \notin \mathbb{Z}$. For example, in $\mathbb{R} \otimes_{\mathbb{Z}} \mathbb{R}$, the elements $(\sqrt{2} \cdot 1) \otimes 1$ and $1 \otimes (\sqrt{2} \cdot 1)$ are distinct. Since the proposed scalar multiplication is ambiguous, $V \otimes_{\mathbb{Z}} W$ does not carry a natural $\mathbb{R}$-vector space structure.


**Structure as a Q-Vector Space.**

**Definition (Torsion-Free and Divisible Modules).**
A $\mathbb{Z}$-module $A$ is ***torsion-free*** if for any non-zero integer $n$, the map $a \mapsto na$ is injective. A $\mathbb{Z}$-module $A$ is ***divisible*** if for any non-zero integer $n$, the map $a \mapsto na$ is surjective.

A $\mathbb{Z}$-module is a vector space over the rational numbers $\mathbb{Q}$ if and only if it is both torsion-free and divisible. Any $\mathbb{R}$-vector space $V$, when viewed as a $\mathbb{Z}$-module, has these properties. It is torsion-free because if $nv = 0$ for $n \neq 0$, then multiplication by $1/n \in \mathbb{R}$ implies $v=0$. It is divisible because for any $v \in V$ and non-zero $n \in \mathbb{Z}$, the equation $nx = v$ has the solution $x = (1/n)v \in V$.

**Theorem (Structure of the Tensor Product).**
Let $V$ and $W$ be vector spaces over $\mathbb{R}$. The abelian group $V \otimes_{\mathbb{Z}} W$ is a vector space over $\mathbb{Q}$.

*Proof.*
Since $V$ and $W$ are $\mathbb{Q}$-vector spaces, the tensor product $V \otimes_{\mathbb{Z}} W$ is also a $\mathbb{Q}$-vector space. Scalar multiplication by $q = m/n \in \mathbb{Q}$ is well-defined on a simple tensor by $q(v \otimes w) = (qv) \otimes w = v \otimes (qw)$. This is well-defined because for any $v' \in V$ such that $v = nv'$, $q(v \otimes w) = m(v' \otimes w) = (mv') \otimes w = ((m/n)nv') \otimes w = (qv) \otimes w$.
$\square$


**Isomorphism and Dimension.**

**Theorem (Isomorphism over Q).**
If $V$ and $W$ are vector spaces over $\mathbb{Q}$, there is a canonical isomorphism of $\mathbb{Q}$-vector spaces:
$$
V \otimes_{\mathbb{Z}} W \cong V \otimes_{\mathbb{Q}} W
$$

*Proof.*
The $\mathbb{Z}$-bilinear map $\phi: V \times W \to V \otimes_{\mathbb{Q}} W$ sending $(v,w)$ to $v \otimes w$ induces a $\mathbb{Z}$-module homomorphism $\Phi: V \otimes_{\mathbb{Z}} W \to V \otimes_{\mathbb{Q}} W$. This map is also $\mathbb{Q}$-linear. The map $\psi: V \times W \to V \otimes_{\mathbb{Z}} W$ is not only $\mathbb{Z}$-bilinear but also $\mathbb{Q}$-bilinear, since for $q \in \mathbb{Q}$, $(qv) \otimes w = v \otimes (qw)$. This induces a homomorphism $\Psi: V \otimes_{\mathbb{Q}} W \to V \otimes_{\mathbb{Z}} W$. The maps $\Phi$ and $\Psi$ are mutually inverse.
$\square$

**Theorem (Dimension of the Tensor Product).**
Let $V$ and $W$ be $\mathbb{R}$-vector spaces with dimensions $d_V = \operatorname{dim}_{\mathbb{R}}(V)$ and $d_W = \operatorname{dim}_{\mathbb{R}}(W)$. The dimension of $V \otimes_{\mathbb{Z}} W$ as a $\mathbb{Q}$-vector space is:
$$
\operatorname{dim}_{\mathbb{Q}}(V \otimes_{\mathbb{Z}} W) = (d_V \cdot d_W) \cdot \mathfrak{c}
$$
where $\mathfrak{c} = |\mathbb{R}|$ is the cardinality of the continuum.

*Proof.*
The dimension of $\mathbb{R}$ as a vector space over $\mathbb{Q}$ is $\operatorname{dim}_{\mathbb{Q}}(\mathbb{R}) = \mathfrak{c}$. For any $\mathbb{R}$-vector space $V$, its dimension over $\mathbb{Q}$ is $\operatorname{dim}_{\mathbb{Q}}(V) = \operatorname{dim}_{\mathbb{R}}(V) \cdot \operatorname{dim}_{\mathbb{Q}}(\mathbb{R}) = d_V \cdot \mathfrak{c}$. Using the isomorphism $V \otimes_{\mathbb{Z}} W \cong V \otimes_{\mathbb{Q}} W$ and the rule for the dimension of a tensor product of vector spaces:
$$
\begin{align*}
\operatorname{dim}_{\mathbb{Q}}(V \otimes_{\mathbb{Z}} W) &= \operatorname{dim}_{\mathbb{Q}}(V \otimes_{\mathbb{Q}} W) \\
&= \operatorname{dim}_{\mathbb{Q}}(V) \cdot \operatorname{dim}_{\mathbb{Q}}(W) \\
&= (d_V \cdot \mathfrak{c}) \cdot (d_W \cdot \mathfrak{c}) \\
&= (d_V \cdot d_W) \cdot \mathfrak{c}^2 \\
&= (d_V \cdot d_W) \cdot \mathfrak{c}
\end{align*}
$$
The final step uses the fact that $\mathfrak{c}^2 = \mathfrak{c}$ in cardinal arithmetic.
$\square$


**Summary and Examples.**

**Example ($\mathbb{R} \otimes_{\mathbb{Z}} \mathbb{R}$).**
Let $V = \mathbb{R}$ and $W = \mathbb{R}$, so $d_V = 1$ and $d_W = 1$. The tensor product $\mathbb{R} \otimes_{\mathbb{Z}} \mathbb{R}$ is a $\mathbb{Q}$-vector space with dimension:
$$
\operatorname{dim}_{\mathbb{Q}}(\mathbb{R} \otimes_{\mathbb{Z}} \mathbb{R}) = (1 \cdot 1) \cdot \mathfrak{c} = \mathfrak{c}
$$

**Example ($\mathbb{R}^2 \otimes_{\mathbb{Z}} \mathbb{R}^3$).**
Let $V = \mathbb{R}^2$ and $W = \mathbb{R}^3$, so $d_V = 2$ and $d_W = 3$. In contrast to the $\mathbb{R}$-vector space $\mathbb{R}^2 \otimes_{\mathbb{R}} \mathbb{R}^3$, which has dimension 6, the tensor product over $\mathbb{Z}$ is a $\mathbb{Q}$-vector space with dimension:
$$
\operatorname{dim}_{\mathbb{Q}}(\mathbb{R}^2 \otimes_{\mathbb{Z}} \mathbb{R}^3) = (2 \cdot 3) \cdot \mathfrak{c} = 6\mathfrak{c} = \mathfrak{c}
$$