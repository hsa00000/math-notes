---
title: Well-Definedness of Derivatives for Smooth Extensions
description: A detailed proof showing that the partial derivatives of a smooth function at a boundary point of the upper half-space are independent of the choice of smooth extension.
date: 2025-09-15T16:35:12+08:00
---

**Independence of Derivatives from Smooth Extension.**

Let $U$ be an open subset of the upper half-space $\mathbb{H}^n = \{ (x^1, \dots, x^n) \in \mathbb{R}^n \mid x^n \geq 0 \}$. Let $f: U \rightarrow \mathbb{R}$ be a smooth function. By definition, for any point $a \in U$, there exists an open neighborhood $\tilde{U} \subseteq \mathbb{R}^n$ of $a$ and a smooth function $\tilde{f}: \tilde{U} \rightarrow \mathbb{R}$ such that $\tilde{f}|_{U \cap \tilde{U}} = f$. Such a function $\tilde{f}$ is called a ***smooth extension*** of $f$. We prove that the partial derivatives of any smooth extension at a boundary point $a \in U \cap \partial \mathbb{H}^n$ are uniquely determined by $f$.

**Theorem (Uniqueness of Derivatives at the Boundary).**

Let $f: U \rightarrow \mathbb{R}$ be a smooth function on an open subset $U \subseteq \mathbb{H}^n$, and let $a \in U \cap \partial \mathbb{H}^n$. If $\tilde{f}_1$ and $\tilde{f}_2$ are two smooth extensions of $f$ defined on a neighborhood of $a$ in $\mathbb{R}^n$, then their partial derivatives at $a$ are identical. That is, for each $i \in \{1, \dots, n\}$,

$$
\frac{\partial \tilde{f}_1}{\partial x^i}(a) = \frac{\partial \tilde{f}_2}{\partial x^i}(a).
$$

*Proof.*
Let $\tilde{f}_1$ and $\tilde{f}_2$ be two smooth extensions of $f$ on an open neighborhood $\tilde{U} \subseteq \mathbb{R}^n$ of $a$. Define the difference function $h: \tilde{U} \rightarrow \mathbb{R}$ by $h = \tilde{f}_1 - \tilde{f}_2$. Since $\tilde{f}_1$ and $\tilde{f}_2$ are smooth, $h$ is also smooth on $\tilde{U}$. Furthermore, for any point $x \in \tilde{U} \cap \mathbb{H}^n$, we have $h(x) = \tilde{f}_1(x) - \tilde{f}_2(x) = f(x) - f(x) = 0$. Thus, $h$ vanishes identically on $\tilde{U} \cap \mathbb{H}^n$.

The proof reduces to showing that all partial derivatives of $h$ at $a$ are zero. This can be shown in two ways.

**Argument from Continuity.**
Since $h$ is smooth, its partial derivatives $\frac{\partial h}{\partial x^i}$ are continuous functions on $\tilde{U}$. On the open set $\tilde{U} \cap \operatorname{Int}(\mathbb{H}^n) = \{x \in \tilde{U} \mid x^n > 0 \}$, the function $h$ is identically zero. Consequently, all its partial derivatives vanish on this open set: $\frac{\partial h}{\partial x^i}(x) = 0$ for all $x \in \tilde{U} \cap \operatorname{Int}(\mathbb{H}^n)$. By the continuity of the partial derivatives, their values at the boundary point $a$ must be the limit of their values from the interior.

$$
\frac{\partial h}{\partial x^i}(a) = \lim_{\substack{x \to a \\ x \in \operatorname{Int}(\mathbb{H}^n)}} \frac{\partial h}{\partial x^i}(x) = \lim_{\substack{x \to a \\ x^n > 0}} 0 = 0.
$$

**Argument from Difference Quotients.**
Alternatively, we compute the derivatives at $a$ directly from their definition. Let $a=(a^1, \dots, a^{n-1}, 0)$.

1.  **Tangential Derivatives ($1 \le i < n$):** The derivative is taken along a direction parallel to the boundary. For sufficiently small $t$, the point $a+te_i$ lies in $\partial \mathbb{H}^n$, so $h(a+te_i) = 0$ and $h(a)=0$.
    
    $$
    \frac{\partial h}{\partial x^i}(a) = \lim_{t \to 0} \frac{h(a+te_i) - h(a)}{t} = \lim_{t \to 0} \frac{0-0}{t} = 0.
    $$

2.  **Normal Derivative ($i=n$):** The derivative is taken in the direction normal to the boundary. Since we must remain in the domain of $h$, we can only take the limit from within $\mathbb{H}^n$.
    
    $$
    \frac{\partial h}{\partial x^n}(a) = \lim_{t \to 0^+} \frac{h(a+te_n) - h(a)}{t} = \lim_{t \to 0^+} \frac{0-0}{t} = 0.
    $$

Both arguments show that $\frac{\partial h}{\partial x^i}(a) = 0$ for all $i=1, \dots, n$. This implies $\frac{\partial \tilde{f}_1}{\partial x^i}(a) - \frac{\partial \tilde{f}_2}{\partial x^i}(a) = 0$, so the derivatives are equal. As a consequence, for any tangent vector $w = \sum w^i \frac{\partial}{\partial x^i}|_a \in T_a\mathbb{R}^n$, the action $w(\tilde{f}) = \sum w^i \frac{\partial \tilde{f}}{\partial x^i}(a)$ is independent of the chosen extension $\tilde{f}$. $\square$