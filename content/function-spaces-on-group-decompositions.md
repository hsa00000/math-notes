---
title: Function Spaces on Group Decompositions
description: This note establishes the well-definedness condition for a class of functions on a group G=AB and describes the structure and basis of the corresponding vector space.
---

**Well-Definedness.**

**Theorem (Well-Definedness).**
Let $G=AB$ with $A, B \le G$ and let $\delta: G \to \mathbb{C}^\times$ be a homomorphism. For a function $\phi: B \to \mathbb{C}$, define a function ***f*** on $G$ by

$$
f(ab) := \delta(a)\phi(b) \quad (a \in A, b \in B).
$$

Then $f$ is well-defined on $G$ if and only if

$$
\phi(xb) = \delta(x)\phi(b) \quad \text{for all } x \in A \cap B, b \in B.
$$

*Proof.*
($\Rightarrow$) If $f$ is well-defined and $x \in A \cap B$, then

$$
\delta(1)\phi(xb) = f(1 \cdot xb) = f(x \cdot b) = \delta(x)\phi(b),
$$

so the relation holds.
($\Leftarrow$) Suppose $\phi(xb) = \delta(x)\phi(b)$ for all $x \in A \cap B$. If $ab = a'b'$ with $a' = ax$ and $b' = x^{-1}b$ for some $x \in A \cap B$, then

$$
\delta(a')\phi(b') = \delta(ax)\phi(x^{-1}b) = \delta(a)\delta(x)\delta(x)^{-1}\phi(b) = \delta(a)\phi(b),
$$

so $f$ is independent of the chosen decomposition. Uniqueness is immediate. $\square$

**Structure and Basis.**

**Theorem (Structure and Basis).**
Let

$$
\Phi_\delta(B) := \{ \phi: B \to \mathbb{C} \mid \phi(xb) = \delta(x)\phi(b) \ \forall x \in A \cap B, b \in B \},
$$

and let $V_\delta := \{ f: G \to \mathbb{C} \mid \exists \phi \in \Phi_\delta(B) \text{ with } f(ab) = \delta(a)\phi(b) \}$. The map

$$
T: \Phi_\delta(B) \to V_\delta, \quad T(\phi)(ab) = \delta(a)\phi(b),
$$

is a linear isomorphism.
If $S \subset B$ is a set of representatives for the left cosets $(A \cap B) \backslash B$, then the family $\{\phi_s\}_{s \in S}$ defined by

$$
\phi_s(xs') =
\begin{cases}
\delta(x), & s'=s, \\
0, & s' \neq s,
\end{cases}
\qquad (x \in A \cap B, s' \in S),
$$

is a basis of $\Phi_\delta(B)$. Consequently, $\{f_s := T(\phi_s)\}_{s \in S}$ is a basis of $V_\delta$. In particular,

$$
\dim V_\delta = |(A \cap B) \backslash B| \quad (\text{finite or infinite}).
$$

*Proof.*
$T$ is well-defined and injective by the previous theorem. Surjectivity is by the definition of $V_\delta$.
For the basis, first $\phi_s \in \Phi_\delta(B)$ since for $x, x_0 \in A \cap B$ and $s' \in S$, letting $b=x_0s'$, we check the condition:

$$
\phi_s(x(x_0 s')) = \begin{cases} \delta(xx_0), & s'=s \\ 0, & s' \neq s \end{cases} = \delta(x)\phi_s(x_0 s').
$$

Spanning: for $\phi \in \Phi_\delta(B)$ set $c_s := \phi(s)$. For $b=xs'$ with $x \in A \cap B$ and $s' \in S$, we have $\sum_{s \in S} c_s \phi_s = \phi$ because

$$
\left(\sum_{s \in S} c_s \phi_s\right)(b) = c_{s'} \delta(x) = \phi(s') \delta(x) = \phi(xs') = \phi(b).
$$

Independence: if $\sum_{s \in S} c_s \phi_s = 0$, evaluate at $s_0 \in S$ to get $c_{s_0} = 0$. Hence all $c_s=0$. Mapping by $T$ preserves linear relations, giving the basis of $V_\delta$. $\square$