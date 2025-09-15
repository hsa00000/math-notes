---
title: Stereographic Projection Atlas for the n-Sphere
description: Defines the standard 2-chart smooth atlas for the n-sphere $S^n$ using stereographic projection and verifies the smoothness of the transition maps.
date: 2025-09-15T10:30:00+08:00
---

**Definition (Stereographic Atlas for $S^n$).**

Let $n \ge 1$. The $n$-sphere $S^n \subset \mathbb{R}^{n+1}$ is the set

$$
S^n = \{ (x, t) \in \mathbb{R}^n \times \mathbb{R} : \|x\|^2 + t^2 = 1 \}.
$$

The north and south poles are $N = (0, \dots, 0, 1)$ and $S = (0, \dots, 0, -1)$, respectively. Define the open sets $U_N = S^n \setminus \{N\}$ and $U_S = S^n \setminus \{S\}$. The charts $\phi_N: U_N \to \mathbb{R}^n$ and $\phi_S: U_S \to \mathbb{R}^n$ are given by stereographic projection:

$$
\phi_N(x, t) = \frac{x}{1-t}, \quad \phi_S(x, t) = \frac{x}{1+t}.
$$

The inverse maps $\phi_N^{-1}: \mathbb{R}^n \to U_N$ and $\phi_S^{-1}: \mathbb{R}^n \to U_S$ are given by

$$
\phi_N^{-1}(y) = \left( \frac{2y}{\|y\|^2 + 1}, \frac{\|y\|^2 - 1}{\|y\|^2 + 1} \right), \quad \phi_S^{-1}(y) = \left( \frac{2y}{\|y\|^2 + 1}, -\frac{\|y\|^2 - 1}{\|y\|^2 + 1} \right).
$$

The ***atlas*** for $S^n$ is the set $\mathcal{A} = \{ (U_N, \phi_N), (U_S, \phi_S) \}$.

**Smoothness of the Atlas.**

*Proof.*
The atlas $\mathcal{A}$ is smooth if its transition maps are smooth. The domain of the transition maps is the overlap $U_N \cap U_S = S^n \setminus \{N, S\}$. The image of this overlap under the charts is $\phi_N(U_N \cap U_S) = \mathbb{R}^n \setminus \{0\}$ and $\phi_S(U_N \cap U_S) = \mathbb{R}^n \setminus \{0\}$.

For any $y \in \mathbb{R}^n \setminus \{0\}$, the transition map $\phi_S \circ \phi_N^{-1}: \mathbb{R}^n \setminus \{0\} \to \mathbb{R}^n \setminus \{0\}$ is computed as follows:

$$
(\phi_S \circ \phi_N^{-1})(y) = \phi_S\left(\frac{2y}{\|y\|^2 + 1}, \frac{\|y\|^2 - 1}{\|y\|^2 + 1}\right) = \frac{\frac{2y}{\|y\|^2 + 1}}{1 + \frac{\|y\|^2 - 1}{\|y\|^2 + 1}} = \frac{2y}{\|y\|^2 + 1} \cdot \frac{\|y\|^2 + 1}{2\|y\|^2} = \frac{y}{\|y\|^2}.
$$

The map $y \mapsto y/\|y\|^2$ is the inversion map on $\mathbb{R}^n \setminus \{0\}$, which is $C^\infty$. This map is its own inverse, so the inverse transition map $\phi_N \circ \phi_S^{-1}$ is identical and also $C^\infty$. Therefore, the charts are smoothly compatible, and $\mathcal{A}$ is a smooth atlas on $S^n$. $\square$