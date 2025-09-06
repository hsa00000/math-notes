---
title: Injectivity of Divisible Modules over PIDs and of Torsion-Free Divisible Modules over Domains
description: Baer's criterion and a uniform annihilation argument yield injectivity results for divisible modules over principal ideal domains and for torsion-free divisible modules over integral domains.
date: 2025-08-03T09:00:00+08:00
---itle: Injectivity of Divisible Modules over PIDs and of Torsion-Free Divisible Modules over Domains
description: Baer’s criterion and a uniform annihilation argument yield injectivity results for divisible modules over principal ideal domains and for torsion-free divisible modules over integral domains.
date: 2025-08-03
---

**Injectivity of Divisible Modules over PIDs and of Torsion-Free Divisible Modules over Domains.**

**Definition (Integral Domain).** A commutative ring $R$ with $1 \neq 0$ is an **_integral domain_** if for all $a,b \in R$, $ab=0$ implies $a=0$ or $b=0$.

**Definition (Principal Ideal Domain).** A commutative ring $R$ with $1 \neq 0$ is a **_principal ideal domain_** if $R$ is an integral domain and every ideal $I \subseteq R$ has the form $I=(a)$ for some $a \in R$.

**Definition (Torsion-Free Module).** Let $R$ be a domain. An $R$-module $M$ is **_torsion-free_** if for all $0 \neq r \in R$ and $m \in M$, $rm=0$ implies $m=0$.

**Definition (Divisible Module).** Let $R$ be a domain. An $R$-module $M$ is **_divisible_** if for every $0 \neq r \in R$ and every $m \in M$ there exists $x \in M$ with $rx=m$.

**Definition (Injective Module).** Let $R$ be a commutative ring with $1 \neq 0$. An $R$-module $M$ is **_injective_** if for every monomorphism of $R$-modules $A \hookrightarrow B$, every $R$-linear map $A \to M$ extends to an $R$-linear map $B \to M$.

**Theorem (Baer’s Criterion).** Let $R$ be a commutative ring with $1 \neq 0$ and let $M$ be an $R$-module. The module $M$ is injective if and only if for every ideal $I \subseteq R$, every $R$-linear map $f:I \to M$ extends to an $R$-linear map $F:R \to M$ with $F|_I=f$.

**Theorem (Divisible over PID $\Rightarrow$ Injective).** Let $R$ be a principal ideal domain and let $M$ be a divisible $R$-module. Then $M$ is injective.

_Proof._ By Baer’s criterion it suffices to extend $f:I \to M$ for an ideal $I \subseteq R$. If $I=(0)$ take $F=0$. If $I=(a)$ with $a \neq 0$, set $m:=f(a)$ and choose $x \in M$ with $ax=m$ by divisibility. Define $F:R \to M$ by $F(r):=rx$. Then for all $r \in R$,

$$
\begin{align*}
F(ar)&=arx=rax=rf(a)=f(ar),
\end{align*}
$$

so $F|_{(a)}=f$. Hence $M$ is injective. $\square$

**Theorem (Torsion-Free Divisible over Domain $\Rightarrow$ Injective).** Let $R$ be an integral domain and let $M$ be an $R$-module that is torsion-free and divisible. Then $M$ is injective.

_Proof._ By Baer’s criterion it is enough to extend $f:I \to M$ for an ideal $I \subseteq R$. If $I=(0)$ take $F=0$. Otherwise choose $0 \neq a \in I$ and set $m_b:=f(b)$ for $b \in I$. By divisibility choose $x \in M$ with $ax=m_a$. For any $b \in I$,

$$
\begin{align*}
a\big(bx-m_b\big)
&=abx-a m_b
= b(ax)-a m_b
= b m_a-a m_b \\
&= f(ba)-f(ab)
= 0.
\end{align*}
$$

Since $a \neq 0$ and $M$ is torsion-free, $bx-m_b=0$. Thus $bx=f(b)$ for all $b \in I$. Define $F:R \to M$ by $F(r):=rx$. Then $F$ is $R$-linear and $F|_I=f$. Hence $M$ is injective. $\square$
