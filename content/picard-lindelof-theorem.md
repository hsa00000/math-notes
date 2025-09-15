---
title: Picard-Lindelöf Theorem
description: Proof of the existence and uniqueness of solutions to first-order ordinary differential equations with Lipschitz continuous vector fields.
date: 2025-09-10T08:47:00+00:00
---

**Definition (Lipschitz Condition).**

Let $(X, d_X)$ and $(Y, d_Y)$ be metric spaces. A function $F: U \subset X \rightarrow Y$ is ***Lipschitz continuous*** on $U$ if there exists a real constant $L \geq 0$ such that for all $\mathbf{x}_1, \mathbf{x}_2 \in U$, the inequality $d_Y(F(\mathbf{x}_1), F(\mathbf{x}_2)) \leq L d_X(\mathbf{x}_1, \mathbf{x}_2)$ holds. The constant $L$ is called a Lipschitz constant for $F$. For a vector field $F: U \subset \mathbb{R}^m \rightarrow \mathbb{R}^m$, this condition, using the Euclidean norm $\| \cdot \|$, is $\|F(\mathbf{x}_1) - F(\mathbf{x}_2)\| \leq L \|\mathbf{x}_1 - \mathbf{x}_2\|$.

**Theorem (Picard-Lindelöf Existence and Uniqueness).**

Let $U \subset \mathbb{R}^m$ be an open set and let $F: U \rightarrow \mathbb{R}^m$ be a Lipschitz continuous vector field. For any initial point $\mathbf{x}_0 \in U$, the initial value problem (IVP)

$$
\begin{cases}
\dfrac{d\mathbf{x}}{dt} = F(\mathbf{x}(t)), & \\[6pt]
\mathbf{x}(0) = \mathbf{x}_0 &
\end{cases}
$$

has a unique solution $\mathbf{x}(t)$ on some time interval $I = [-\alpha, \alpha]$ for some $\alpha > 0$. Furthermore, this solution depends continuously on the initial condition $\mathbf{x}_0$.

*Proof.*
The proof consists of three main parts: 1) reformulation of the IVP as an integral equation and definition of a mapping, 2) application of the Banach Fixed-Point Theorem to show existence and uniqueness of a fixed point, and 3) demonstration of continuous dependence on the initial condition.

**Part 1: Integral Equation Formulation.**
A function $\mathbf{x}(t)$ is a solution to the IVP if and only if it is continuous and satisfies the integral equation:

$$
\mathbf{x}(t) = \mathbf{x}_0 + \int_0^t F(\mathbf{x}(s)) \, ds
$$

This equivalence follows from the Fundamental Theorem of Calculus. A solution to this integral equation is a fixed point of the operator $\mathcal{T}$ defined by:

$$
(\mathcal{T}\mathbf{y})(t) = \mathbf{x}_0 + \int_0^t F(\mathbf{y}(s)) \, ds
$$

Let's define a suitable metric space for this operator. Since $\mathbf{x}_0 \in U$ and $U$ is open, there exists $b > 0$ such that the closed ball $\bar{B}(\mathbf{x}_0, b) = \{ \mathbf{y} \in \mathbb{R}^m : \|\mathbf{y} - \mathbf{x}_0\| \leq b \}$ is contained in $U$. Since $F$ is continuous on the compact set $\bar{B}(\mathbf{x}_0, b)$, it is bounded there. Let $M = \sup_{\mathbf{y} \in \bar{B}(\mathbf{x}_0, b)} \|F(\mathbf{y})\|$.

Choose $\alpha > 0$ such that $\alpha \leq b/M$ and $\alpha L < 1$, where $L$ is the Lipschitz constant of $F$. Let $I_\alpha = [-\alpha, \alpha]$. Let $X = C(I_\alpha, \bar{B}(\mathbf{x}_0, b))$ be the space of continuous functions from $I_\alpha$ to $\bar{B}(\mathbf{x}_0, b)$. This space, equipped with the supremum norm $\|\mathbf{y}_1 - \mathbf{y}_2\|_{\infty} = \sup_{t \in I_\alpha} \|\mathbf{y}_1(t) - \mathbf{y}_2(t)\|$, is a complete metric space.

We show that $\mathcal{T}$ maps $X$ to itself. For any $\mathbf{y} \in X$ and $t \in I_\alpha$:
$$
\|(\mathcal{T}\mathbf{y})(t) - \mathbf{x}_0\| = \left\| \int_0^t F(\mathbf{y}(s)) \, ds \right\| \leq \left| \int_0^t \|F(\mathbf{y}(s))\| \, ds \right| \leq M|t| \leq M\alpha \leq b
$$
Thus, $(\mathcal{T}\mathbf{y})(t) \in \bar{B}(\mathbf{x}_0, b)$ for all $t \in I_\alpha$. Since the integral of a continuous function is continuous, $\mathcal{T}\mathbf{y}$ is a continuous function. Therefore, $\mathcal{T}: X \rightarrow X$.

**Part 2: Contraction Mapping.**
Now we show that $\mathcal{T}$ is a contraction mapping on $X$. Let $\mathbf{y}_1, \mathbf{y}_2 \in X$.
$$
\begin{align*}
\|(\mathcal{T}\mathbf{y}_1)(t) - (\mathcal{T}\mathbf{y}_2)(t)\| &= \left\| \int_0^t (F(\mathbf{y}_1(s)) - F(\mathbf{y}_2(s))) \, ds \right\| \\
&\leq \left| \int_0^t \|F(\mathbf{y}_1(s)) - F(\mathbf{y}_2(s))\| \, ds \right| \\
&\leq \left| \int_0^t L \|\mathbf{y}_1(s) - \mathbf{y}_2(s)\| \, ds \right| \\
&\leq L \left| \int_0^t \|\mathbf{y}_1 - \mathbf{y}_2\|_{\infty} \, ds \right| \\
&\leq L |t| \|\mathbf{y}_1 - \mathbf{y}_2\|_{\infty} \leq L\alpha \|\mathbf{y}_1 - \mathbf{y}_2\|_{\infty}
\end{align*}
$$
Taking the supremum over $t \in I_\alpha$:
$$
\|\mathcal{T}\mathbf{y}_1 - \mathcal{T}\mathbf{y}_2\|_{\infty} \leq (L\alpha) \|\mathbf{y}_1 - \mathbf{y}_2\|_{\infty}
$$
Since we chose $\alpha$ such that $L\alpha < 1$, $\mathcal{T}$ is a contraction on the complete metric space $X$. By the Banach Fixed-Point Theorem, $\mathcal{T}$ has a unique fixed point $\mathbf{x} \in X$. This fixed point is the unique solution to the IVP on the interval $I_\alpha$.

**Part 3: Continuous Dependence on Initial Conditions.**
Let $\mathbf{x}(t; \mathbf{x}_0)$ be the unique solution for the initial condition $\mathbf{x}_0$. Let $\mathbf{z}_0$ be another initial condition close to $\mathbf{x}_0$, and let $\mathbf{z}(t; \mathbf{z}_0)$ be its corresponding solution. Both solutions exist on an interval $[-\alpha, \alpha]$ for a sufficiently small $\alpha$.

$$
\mathbf{x}(t) = \mathbf{x}_0 + \int_0^t F(\mathbf{x}(s)) \, ds
$$
$$
\mathbf{z}(t) = \mathbf{z}_0 + \int_0^t F(\mathbf{z}(s)) \, ds
$$
Subtracting these equations gives:
$$
\mathbf{x}(t) - \mathbf{z}(t) = (\mathbf{x}_0 - \mathbf{z}_0) + \int_0^t (F(\mathbf{x}(s)) - F(\mathbf{z}(s))) \, ds
$$
Taking norms and using the triangle inequality and Lipschitz condition:
$$
\|\mathbf{x}(t) - \mathbf{z}(t)\| \leq \|\mathbf{x}_0 - \mathbf{z}_0\| + \left| \int_0^t \|F(\mathbf{x}(s)) - F(\mathbf{z}(s))\| \, ds \right|
$$
$$
\|\mathbf{x}(t) - \mathbf{z}(t)\| \leq \|\mathbf{x}_0 - \mathbf{z}_0\| + L \left| \int_0^t \|\mathbf{x}(s) - \mathbf{z}(s)\| \, ds \right|
$$
Let $\phi(t) = \|\mathbf{x}(t) - \mathbf{z}(t)\|$. For $t \geq 0$, we have $\phi(t) \leq \|\mathbf{x}_0 - \mathbf{z}_0\| + L \int_0^t \phi(s) \, ds$.
By Gronwall's inequality, this implies:
$$
\phi(t) \leq \|\mathbf{x}_0 - \mathbf{z}_0\| e^{Lt}
$$
For any $t \in [-\alpha, \alpha]$, we have $e^{L|t|} \leq e^{L\alpha}$. Therefore:
$$
\|\mathbf{x}(t; \mathbf{x}_0) - \mathbf{z}(t; \mathbf{z}_0)\|_{\infty} \leq \|\mathbf{x}_0 - \mathbf{z}_0\| e^{L\alpha}
$$
This inequality shows that the solution map $\mathbf{x}_0 \mapsto \mathbf{x}(t; \mathbf{x}_0)$ is continuous (in fact, Lipschitz continuous) on the space of initial conditions. If $\|\mathbf{x}_0 - \mathbf{z}_0\| \to 0$, then $\|\mathbf{x}(t; \mathbf{x}_0) - \mathbf{z}(t; \mathbf{z}_0)\|_{\infty} \to 0$, which is the definition of continuous dependence.
$\square$