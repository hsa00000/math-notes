---
title: Equivalence of Definitions of a Regular Map
description: A proof demonstrating that the two standard definitions of a regular map between quasiprojective varieties are equivalent.
date: 2025-09-05T09:00:00+08:00
---

**Definitions.**

**Definition (Regular Map 1).**
Let $X \subseteq \mathbb{P}^m$ and $Y \subseteq \mathbb{P}^n$ be quasiprojective varieties over a field $K$. A map $F: X \to Y$ is a ***regular map*** if for every point $p \in X$, there exist homogeneous polynomials $f_0, \ldots, f_n \in K[x_0, \ldots, x_m]$ of the same degree such that $p \notin \mathcal{V}(f_0, \ldots, f_n)$ and $F(a) = [f_0(a) : \cdots : f_n(a)]$ for all $a \in X \setminus \mathcal{V}(f_0, \ldots, f_n)$.

**Definition (Regular Map 2).**
Let $X \subseteq \mathbb{P}^m$ and $Y \subseteq \mathbb{P}^n$ be quasiprojective varieties over a field $K$. A map $F: X \to Y$ is a ***regular map*** if for every point $p \in X$, there exists an open neighborhood $U \subseteq X$ of $p$ and $n+1$ homogeneous polynomials $f_0, \ldots, f_n \in K[x_0, \ldots, x_m]$ of the same degree such that for every point $a \in U$, at least one $f_i(a)$ is non-zero, and $F(a) = [f_0(a) : \cdots : f_n(a)]$.

**Theorem (Equivalence of Definitions).**

The two definitions of a regular map are equivalent.

*Proof.*
Let $F: X \to Y$ be a map between quasiprojective varieties.

($1 \Rightarrow 2$) Assume $F$ satisfies Definition (1). Let $p \in X$. By assumption, there exist homogeneous polynomials $f_0, \ldots, f_n$ of the same degree such that $p \notin \mathcal{V}(f_0, \ldots, f_n)$. Let $U = X \setminus \mathcal{V}(f_0, \ldots, f_n)$. The set $\mathcal{V}(f_0, \ldots, f_n)$ is closed in the Zariski topology, so $U$ is an open subset of $X$. Since $p \in U$, it is an open neighborhood of $p$. By construction of $U$, for any $a \in U$, at least one $f_i(a)$ is non-zero. Definition (1) states that $F(a) = [f_0(a) : \cdots : f_n(a)]$ for all $a \in U$. Thus, $F$ satisfies Definition (2).

($2 \Rightarrow 1$) Assume $F$ satisfies Definition (2). Let $p \in X$. By assumption, there exists an open neighborhood $U \subseteq X$ of $p$ and homogeneous polynomials $f_0, \ldots, f_n$ of the same degree such that for any $a \in U$, at least one $f_i(a) \neq 0$ and $F(a) = [f_0(a) : \cdots : f_n(a)]$. Since $p \in U$, it follows that at least one $f_i(p) \neq 0$, which implies $p \notin \mathcal{V}(f_0, \ldots, f_n)$. Let $V = X \setminus \mathcal{V}(f_0, \ldots, f_n)$. The set $V$ is an open subset of $X$ containing $U$. Let $G: V \to Y$ be the map defined by $G(a) = [f_0(a) : \cdots : f_n(a)]$. Both $F$ and $G$ are regular maps, and they agree on the non-empty open set $U$. Two regular maps that agree on a non-empty open subset of a quasiprojective variety must be identical on the intersection of their domains. Thus, $F(a) = G(a)$ for all $a \in V$. This means $F(a) = [f_0(a) : \cdots : f_n(a)]$ for all $a \in X \setminus \mathcal{V}(f_0, \ldots, f_n)$. Therefore, $F$ satisfies Definition (1). $\square$