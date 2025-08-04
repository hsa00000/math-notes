---
title: Application of Nagata's Criterion for Factoriality
description: An example demonstrating the use of Nagata's Criterion to prove that the coordinate ring of the real 2-sphere is a Unique Factorization Domain (UFD).
---

**Definition.**
A noetherian integral domain $R$ is a ***Unique Factorization Domain (UFD)*** if every non-zero non-unit element can be written as a product of prime elements.

**Theorem 1 (Nagata's Criterion for Factoriality).**
Let $A$ be a noetherian integral domain and let $s \in A$ be a non-zero, non-unit element. If $s$ is a prime element and the localization $A_s$ is a UFD, then $A$ is a UFD.

**Theorem 2 (Coordinate Ring of the Real Sphere is a UFD).**
Let $k = \mathbb{R}$ be the field of real numbers. The ring $A = \mathbb{R}[x, y, z] / (x^2 + y^2 + z^2 - 1)$ is a UFD.

*Proof.*
The proof proceeds by applying Nagata's Criterion to the ring $A$ with a specific choice of a prime element.

First, $A$ is a noetherian integral domain. The ring $\mathbb{R}[x, y, z]$ is noetherian, so its quotient $A$ is noetherian. The polynomial $p(x, y, z) = x^2 + y^2 + z^2 - 1$ is irreducible over $\mathbb{R}$, which implies the principal ideal $(p)$ is a prime ideal. Therefore, $A$ is an integral domain.

Let $s = 1 - z \in A$. The element $s$ is not a unit in $A$, since if it were, $A/(s)$ would be the zero ring. We show $s$ is a prime element by demonstrating that the quotient ring $A/(s)$ is an integral domain.

$$
A/(s) = (\mathbb{R}[x, y, z] / (x^2 + y^2 + z^2 - 1)) / (1 - z) \cong \mathbb{R}[x, y, z] / (x^2 + y^2 + z^2 - 1, 1 - z)
$$

Substituting $z=1$ into the first relation yields the isomorphism:

$$
A/(s) \cong \mathbb{R}[x, y] / (x^2 + y^2 + 1^2 - 1) \cong \mathbb{R}[x, y] / (x^2 + y^2)
$$

The polynomial $x^2 + y^2$ is irreducible in $\mathbb{R}[x, y]$. Thus, the ideal $(x^2 + y^2)$ is a prime ideal, and the quotient ring $\mathbb{R}[x, y] / (x^2 + y^2)$ is an integral domain. Consequently, $s = 1-z$ is a prime element in $A$.

Next, we show that the localization $A_s = A_{1-z}$ is a UFD. This localization corresponds to the ring of regular functions on the sphere excluding the point $(0,0,1)$. We define an isomorphism $\phi: \mathbb{R}[u, v] \to A_{1-z}$ induced by the stereographic projection. The map is defined by sending $u$ and $v$ to elements of $A_{1-z}$:

$$
\phi(u) = \frac{x}{1-z}, \quad \phi(v) = \frac{y}{1-z}
$$

The inverse map is given by:

$$
z = \frac{u^2+v^2-1}{u^2+v^2+1}, \quad x = u(1-z) = \frac{2u}{u^2+v^2+1}, \quad y = v(1-z) = \frac{2v}{u^2+v^2+1}
$$

These establish a biregular correspondence between the punctured sphere and the plane $\mathbb{R}^2$, inducing an isomorphism of coordinate rings $A_{1-z} \cong \mathbb{R}[u, v]$.

The ring $\mathbb{R}[u, v]$ is a polynomial ring in two variables over a field, which is a UFD. Therefore, $A_{1-z}$ is a UFD.

Since $A$ is a noetherian integral domain, $s=1-z$ is a prime element in $A$, and the localization $A_s$ is a UFD, Nagata's Criterion implies that $A$ is a UFD.
$\square$