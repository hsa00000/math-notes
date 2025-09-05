---
title: Regular Maps and Regular Functions
description: Establishes the one-to-one correspondence between regular maps from a quasiprojective variety to the affine line and regular functions on that variety, with an example of a regular map on projective space.
---

**Definitions.**

**Definition (Regular Function).**
Let $X \subseteq \mathbb{P}^m$ be a quasiprojective variety over a field $K$. A function $f: X \to K$ is said to be ***regular*** on $X$ if for every point $p \in X$, there exists an open neighborhood $U \subseteq X$ of $p$ and two homogeneous polynomials $g, h \in K[x_0, \dots, x_m]$ of the same degree such that $h(a) \neq 0$ for all $a \in U$, and for all $a \in U$, the function is given by $f(a) = g(a)/h(a)$.

**Definition (Regular Map).**
Let $X \subseteq \mathbb{P}^m$ and $Y \subseteq \mathbb{P}^n$ be quasiprojective varieties over a field $K$. A map $F: X \to Y$ is a ***regular map*** if for every point $p \in X$, there exists an open neighborhood $U \subseteq X$ of $p$ and $n+1$ homogeneous polynomials $f_0, \dots, f_n \in K[x_0, \dots, x_m]$ of the same degree such that for every point $a \in U$, at least one $f_i(a)$ is non-zero, and $F(a) = [f_0(a) : \dots : f_n(a)]$.

**Correspondence with the Affine Line.**

**Theorem (Regular Maps to the Affine Line).**
Let $X \subseteq \mathbb{P}^m$ be a quasiprojective variety over a field $K$, and let $\mathbb{A}^1$ be the affine line over $K$. There is a one-to-one correspondence between the set of regular maps $F: X \to \mathbb{A}^1$ and the set of regular functions $f: X \to K$.

*Proof.*
We establish the correspondence by constructing a unique regular function from a regular map, and conversely.

First, let $F: X \to \mathbb{A}^1$ be a regular map. We view $\mathbb{A}^1$ as the open subset of $\mathbb{P}^1$ via the embedding $c \mapsto [1:c]$. Thus, $F$ is a regular map to $\mathbb{P}^1$ whose image lies in the open set where the first coordinate is non-zero. By definition, for any $p \in X$, there exists an open neighborhood $U \subseteq X$ of $p$ and homogeneous polynomials $f_0, f_1 \in K[x_0, \dots, x_m]$ of the same degree such that $F(a) = [f_0(a) : f_1(a)]$ for all $a \in U$. Since the image of $F$ is contained in $\mathbb{A}^1$, we must have $f_0(a) \neq 0$ for all $a \in X$. We define a function $f: X \to K$ by setting $f(a) = f_1(a)/f_0(a)$. This local representation as a ratio of homogeneous polynomials of the same degree where the denominator is non-vanishing is the definition of a regular function. If $F(a) = [g_0(a) : g_1(a)]$ is another local representation on some open set, then $[f_0(a) : f_1(a)] = [g_0(a) : g_1(a)]$ implies $f_0(a)g_1(a) = f_1(a)g_0(a)$. As $f_0(a)$ and $g_0(a)$ are non-zero, it follows that $f_1(a)/f_0(a) = g_1(a)/g_0(a)$, so the function $f$ is uniquely determined by $F$.

Conversely, let $f: X \to K$ be a regular function. By definition, for every point $p \in X$, there exists a neighborhood $U \subseteq X$ and two homogeneous polynomials $g, h \in K[x_0, \dots, x_m]$ of the same degree such that $h(p) \neq 0$ and $f(a) = g(a)/h(a)$ for all $a \in U$. We define a map $F: X \to \mathbb{P}^1$ by $F(a) = [h(a) : g(a)]$. Since $h(p) \neq 0$ for any $p$, at least one of the components of $[h(p):g(p)]$ is non-zero, so this defines a regular map. Furthermore, since $h(a)$ is locally non-zero, the image of $F$ lies in the open subset of $\mathbb{P}^1$ where the first coordinate is non-zero, which is isomorphic to $\mathbb{A}^1$. Thus, $F$ is a regular map from $X$ to $\mathbb{A}^1$. If $f(a) = g'(a)/h'(a)$ is another local representation, then $g(a)/h(a) = g'(a)/h'(a)$, which implies $g(a)h'(a) = h(a)g'(a)$. This is the condition for $[h(a) : g(a)]$ and $[h'(a) : g'(a)]$ to define the same point in $\mathbb{P}^1$, so the map $F$ is uniquely determined by $f$.

The two constructions are inverse to each other, establishing the one-to-one correspondence.
$\square$

**Example of a Regular Map on Projective Space.**

**Theorem (Swapping Map on $\mathbb{P}^1$).**
The map $F: \mathbb{P}^1 \to \mathbb{P}^1$ defined by $F([x_0:x_1]) = [x_1:x_0]$ is a regular map that is not induced by a regular function.

*Proof.*
First, we show $F$ is a regular map. The map is defined by homogeneous polynomials $f_0(x_0, x_1) = x_1$ and $f_1(x_0, x_1) = x_0$. Both are homogeneous of degree 1. Their only common zero in $\mathbb{A}^2$ is $(0,0)$, which does not correspond to any point in $\mathbb{P}^1$. Thus, for any $p \in \mathbb{P}^1$, at least one of $f_0(p)$ or $f_1(p)$ is non-zero, so $F$ is a regular map.

Next, we prove by contradiction that $F$ cannot be induced by a single regular function. Assume $F$ is induced by a regular function $f: \mathbb{P}^1 \to K$. According to the correspondence, this implies that the image of $F$ is contained in an affine chart of $\mathbb{P}^1$ and can be written as $F(p) = [1:f(p)]$ for all $p \in \mathbb{P}^1$. However, any regular function on a projective variety, such as $\mathbb{P}^1$, must be a constant function. Thus, there exists some $c \in K$ such that $f(p) = c$ for all $p \in \mathbb{P}^1$. This would mean $F$ is the constant map $F(p) = [1:c]$. But the given map $F([x_0:x_1]) = [x_1:x_0]$ is not constant. For example, $F([1:0]) = [0:1]$ and $F([1:1]) = [1:1]$. Since $[0:1]$ and $[1:1]$ are different points in $\mathbb{P}^1$, the map is not constant. This is a contradiction. Therefore, the map $F$ is not induced by a regular function.
$\square$