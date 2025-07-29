<!-- injectivity-of-divisible-modules-over-a-pid.md -->
---
title: Injectivity of Divisible Modules over a PID
description: A proof that a module over a PID is injective if and only if it is divisible, with the corollary that Q/Z is an injective Z-module.
---

**Definition.**

Let $R$ be an integral domain. An $R$-module $M$ is ***divisible*** if for every $m \in M$ and every non-zero $r \in R$, there exists an element $x \in M$ such that $rx = m$.

**Theorem.**

Let $R$ be a Principal Ideal Domain (PID). An $R$-module $D$ is injective if and only if it is divisible.

*Proof.*
Assume $D$ is an injective $R$-module. Let $d \in D$ and $0 \neq r \in R$. Consider the ideal $I = (r)$. Define an $R$-module homomorphism $f: (r) \to D$ by $f(sr) = sd$. This map is well-defined as $R$ is an integral domain. By the injectivity of $D$, there exists an extension $\tilde{f}: R \to D$ such that $\tilde{f}|_{(r)} = f$. Let $x = \tilde{f}(1) \in D$. Then $rx = r\tilde{f}(1) = \tilde{f}(r) = f(r) = d$. Thus, $D$ is divisible.

Conversely, assume $D$ is a divisible $R$-module. By Baer's Criterion, it suffices to show that any homomorphism $f: I \to D$ from an ideal $I$ of $R$ extends to a homomorphism $\tilde{f}: R \to D$. Since $R$ is a PID, $I=(r)$ for some $r \in R$. If $r=0$, the extension is trivial. Assume $r \neq 0$. Let $f(r) = d \in D$. As $D$ is divisible, there exists an element $x \in D$ such that $rx=d$. Define $\tilde{f}: R \to D$ by $\tilde{f}(s) = sx$. This is an $R$-module homomorphism. For any element $sr \in (r)$, we have $\tilde{f}(sr) = (sr)x = s(rx) = sd$. We also have $f(sr) = sf(r) = sd$. Thus, $\tilde{f}$ extends $f$. By Baer's Criterion, $D$ is an injective $R$-module.
$\\square$

**Theorem.**

The $\mathbb{Z}$-module $\mathbb{Q}/\mathbb{Z}$ is injective.

*Proof.*
The ring of integers $\mathbb{Z}$ is a PID. We show that $\mathbb{Q}/\mathbb{Z}$ is a divisible $\mathbb{Z}$-module. Let $q + \mathbb{Z} \in \mathbb{Q}/\mathbb{Z}$ for some $q \in \mathbb{Q}$, and let $n \in \mathbb{Z}$ be a non-zero integer. We seek an element $x + \mathbb{Z} \in \mathbb{Q}/\mathbb{Z}$ such that $n(x+\mathbb{Z}) = q+\mathbb{Z}$. Let $x = q/n$. Since $q \in \mathbb{Q}$ and $n \in \mathbb{Z}$ is non-zero, $x \in \mathbb{Q}$. Then $n(x+\mathbb{Z}) = nx + \mathbb{Z} = n(q/n) + \mathbb{Z} = q + \mathbb{Z}$. Thus, $\mathbb{Q}/\mathbb{Z}$ is divisible. Since $\mathbb{Z}$ is a PID and $\mathbb{Q}/\mathbb{Z}$ is a divisible $\mathbb{Z}$-module, it is injective by the preceding theorem.
$\square$