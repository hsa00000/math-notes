---
title: The Tor Functor is Balanced
description: A proof that the left derived functors of M ⊗_R - and - ⊗_R N are naturally isomorphic, establishing that Tor is a balanced bifunctor.
---

**Definition.**

Let $R$ be a ring, $M$ a right $R$-module, and $N$ a left $R$-module. The functor $\operatorname{Tor}_n^R(M, N)$ is defined as the $n$-th homology of the complex $P_* \otimes_R N$, where $P_* \to M$ is a projective resolution of $M$. Alternatively, one can define $\overline{\operatorname{Tor}}_n^R(M, N)$ as the $n$-th homology of the complex $M \otimes_R Q_*$, where $Q_* \to N$ is a projective resolution of $N$. The bifunctor $\operatorname{Tor}_n^R(-,-)$ is ***balanced*** if there exists a natural isomorphism $\operatorname{Tor}_n^R(M, N) \cong \overline{\operatorname{Tor}}_n^R(M, N)$ for all $M, N$ and $n \ge 0$.

**Theorem.**

For any ring $R$, right $R$-module $M$, and left $R$-module $N$, there exists a natural isomorphism $\operatorname{Tor}_n^R(M, N) \cong \overline{\operatorname{Tor}}_n^R(M, N)$ for all $n \ge 0$.

*Proof.*
Let $P_* \to M$ be a projective resolution of $M$ and $Q_* \to N$ be a projective resolution of $N$. Construct the double complex $C_{p,q} = P_p \otimes_R Q_q$ for $p, q \ge 0$. The homology of the total complex $\operatorname{Tot}(C)$ will be computed in two ways using the two spectral sequences of a double complex.

First, consider the spectral sequence $'E$ arising from filtering by the column index $q$. The first page is given by the homology of the rows:

$$
'E^1_{p,q} = H_p(C_{*,q}) = H_p(P_* \otimes_R Q_q)
$$

Since each $Q_q$ is a projective $R$-module, it is flat. The functor $-\otimes_R Q_q$ is exact, thus it commutes with homology.

$$
H_p(P_* \otimes_R Q_q) \cong H_p(P_*) \otimes_R Q_q = \begin{cases} M \otimes_R Q_q & p=0 \\ 0 & p>0 \end{cases}
$$

The second page is the homology of the first page with respect to the vertical differential:

$$
'E^2_{p,q} = H_q('E^1_{p,*}) = \begin{cases} H_q(M \otimes_R Q_*) & p=0 \\ 0 & p>0 \end{cases}
$$

By definition, $H_q(M \otimes_R Q_*) = \overline{\operatorname{Tor}}_q^R(M, N)$. The spectral sequence collapses at the $E^2$ page, yielding $H_n(\operatorname{Tot}(C)) \cong \overline{\operatorname{Tor}}_n^R(M, N)$.

Second, consider the spectral sequence $''E$ arising from filtering by the row index $p$. The first page is given by the homology of the columns:

$$
''E^1_{p,q} = H_q(C_{p,*}) = H_q(P_p \otimes_R Q_*)
$$

Since each $P_p$ is a projective $R$-module, it is flat. The functor $P_p \otimes_R -$ is exact.

$$
H_q(P_p \otimes_R Q_*) \cong P_p \otimes_R H_q(Q_*) = \begin{cases} P_p \otimes_R N & q=0 \\ 0 & q>0 \end{cases}
$$

The second page is the homology of the first page with respect to the horizontal differential:

$$
''E^2_{p,q} = H_p(''E^1_{*,q}) = \begin{cases} H_p(P_* \otimes_R N) & q=0 \\ 0 & q>0 \end{cases}
$$

By definition, $H_p(P_* \otimes_R N) = \operatorname{Tor}_p^R(M, N)$. This spectral sequence also collapses at the $E^2$ page, yielding $H_n(\operatorname{Tot}(C)) \cong \operatorname{Tor}_n^R(M, N)$.

Both spectral sequences converge to the homology of the same total complex. Therefore, there is a natural isomorphism $\operatorname{Tor}_n^R(M, N) \cong \overline{\operatorname{Tor}}_n^R(M, N)$.
$\square$