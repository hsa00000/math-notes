---
title: "Torsion-Free and Divisible Modules over an Integral Domain"
description: "Equivalence with K-vector spaces via the fraction field and a construction of the scalar action; generalization to total quotient rings."
date: 2025-08-28T10:00:00+08:00
---

**Definitions.**

**Definition (Torsion-Free and Divisible).**
Let $R$ be an integral domain and let $M$ be an $R$-module. The module $M$ is ***torsion-free*** if for every non-zero $r \in R$ and any $x \in M$, the relation $rx=0$ implies $x=0$. The module $M$ is ***divisible*** if for every non-zero $r \in R$ and every $x \in M$, there exists some $y \in M$ such that $ry=x$.

**Main Result.**

**Theorem (Characterization via Torsion-Free and Divisibility).**
Let $R$ be an integral domain with fraction field $K = \operatorname{Frac}(R)$, and let $M$ be an $R$-module. Then $M$ can be given the structure of a $K$-vector space that extends its $R$-module structure if and only if $M$ is a torsion-free and divisible $R$-module.

*Proof.*
($\Rightarrow$) Suppose $M$ is a $K$-vector space with an action compatible with the $R$-action. Let $r \in R \setminus \{0\}$ and $x \in M$. If $rx=0$, then since $r$ is invertible in $K$, $x = (r^{-1}r)x = r^{-1}(rx) = r^{-1}(0) = 0$. Thus, $M$ is torsion-free. For divisibility, let $r \in R \setminus \{0\}$ and $x \in M$. Let $y = r^{-1}x \in M$. Then $ry = r(r^{-1}x) = (rr^{-1})x = 1x = x$. Thus, $M$ is divisible.

($\Leftarrow$) Assume $M$ is a torsion-free and divisible $R$-module. We define the action of $k=a/b \in K$ on $x \in M$ to be the unique element $y \in M$ such that $by=ax$. Existence of such a $y$ is guaranteed by divisibility, as $ax \in M$ and $b \neq 0$. Uniqueness is guaranteed by torsion-freeness, since if $by_1 = by_2$, then $b(y_1-y_2)=0$, which implies $y_1=y_2$ as $b \neq 0$.

The action is well-defined. If $a/b=c/d$, then $ad=bc$. Let $y_1=(a/b)\cdot x$ and $y_2=(c/d)\cdot x$, so $by_1=ax$ and $dy_2=cx$. Then
$$
db(y_1-y_2) = d(by_1) - b(dy_2) = d(ax) - b(cx) = (ad-bc)x = 0.
$$
Since $db \neq 0$ and $M$ is torsion-free, $y_1-y_2=0$.

The vector space axioms are verified by clearing denominators and applying torsion-freeness. For $k=a/b, k'=c/d \in K$ and $x, z \in M$:
$$
b(k\cdot(x+z) - k\cdot x - k\cdot z) = a(x+z) - ax - az = 0.
$$
$$
bd((k+k')\cdot x - k\cdot x - k'\cdot x) = (ad+bc)x - d(ax) - b(cx) = 0.
$$
$$
bd((kk')\cdot x - k\cdot(k'\cdot x)) = acx - a(d(k'\cdot x)) = acx - a(cx) = 0.
$$
The identity axiom $1\cdot x = x$ follows from the definition with $1=1/1$. The action extends the $R$-action, since for $r \in R$, $(r/1)\cdot x$ is the unique $y$ with $1\cdot y = rx$, so $y=rx$.
$\square$

**Generalization.**

**Definition (S-Torsion-Free and S-Divisible Module).**
Let $R$ be a commutative ring and let $S \subseteq R$ be a multiplicative set consisting of non-zero-divisors. An $R$-module $M$ is ***$S$-torsion-free*** if for every $s \in S$ and $x \in M$, the relation $sx=0$ implies $x=0$. The module $M$ is ***$S$-divisible*** if for every $s \in S$ and every $x \in M$, there exists some $y \in M$ such that $sy=x$.

**Theorem (Extension to the Ring of Fractions).**
Let $R$ be a commutative ring, $S \subseteq R$ a multiplicative set of non-zero-divisors, and $M$ an $R$-module. Let $Q = S^{-1}R$ be the ring of fractions. The $R$-module $M$ admits a unique $Q$-module structure that extends the $R$-action if and only if $M$ is $S$-torsion-free and $S$-divisible.

*Proof.*
($\Rightarrow$) Assume $M$ has a $Q$-module structure extending the $R$-action. For any $s \in S$, its image $s/1 \in Q$ is a unit. If $sx=0$, then $x = (1/s)(sx)=0$, so $M$ is $S$-torsion-free. For any $x \in M$, let $y=(1/s)x$. Then $sy=x$, so $M$ is $S$-divisible.

($\Leftarrow$) Assume $M$ is $S$-torsion-free and $S$-divisible. Define the action of $a/s \in Q$ on $x \in M$ to be the unique $y \in M$ such that $sy=ax$. Existence follows from $S$-divisibility and uniqueness from $S$-torsion-freeness. For well-definedness, if $a/s=a'/s'$, there exists $t \in S$ with $t(as'-a's)=0$. Let $y=(a/s)\cdot x$ and $y'=(a'/s')\cdot x$. Then
$$
tss'(y-y') = ts'(sy) - ts(s'y') = ts'(ax) - ts(a'x) = t(as'-a's)x = 0.
$$
Since $tss' \in S$ and $M$ is $S$-torsion-free, $y=y'$. The module axioms are verified by clearing denominators, analogously to the integral domain case. The uniqueness of the structure follows because any compatible structure $*$ must satisfy $sy=ax$ for $y=(a/s)*x$, which uniquely determines $y$.
$\square$