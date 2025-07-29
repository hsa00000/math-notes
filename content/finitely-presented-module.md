---
title: Finitely Generated Modules over Noetherian Rings are Finitely Presented
description: Concise proof that every finitely generated module over a Noetherian ring admits a finite presentation.
---

**Definition (Noetherian ring).**  
A ring $R$ is *Noetherian* if every ideal of $R$ is finitely generated.

**Definition (Finitely generated module).**  
An $R$‑module $M$ is *finitely generated* if there exists a surjection $R^{\oplus n}\twoheadrightarrow M$ for some $n\in\mathbb N$.

**Definition (Finitely presented module).**  
An $R$‑module $M$ is *finitely presented* if there is an exact sequence  
$$
R^{\oplus m}\longrightarrow R^{\oplus n}\longrightarrow M\longrightarrow 0
$$
with $m,n\in\mathbb N$.

**Theorem.**  
If $R$ is Noetherian and $M$ is a finitely generated $R$‑module, then $M$ is finitely presented.

*Proof.*  
Choose a surjection  
$$
\varphi : R^{\oplus n}\twoheadrightarrow M.
$$
Let $K = \ker \varphi$. Because $R^{\oplus n}$ is Noetherian, $K$ is finitely generated; choose generators $k_1,\dots,k_m$ and define  
$$
\psi : R^{\oplus m}\longrightarrow R^{\oplus n}, \qquad e_j \mapsto k_j .
$$
Then  
$$
R^{\oplus m}\xrightarrow{\;\psi\;}R^{\oplus n}\xrightarrow{\;\varphi\;}M\longrightarrow 0
$$
is exact, yielding a finite presentation of $M$. $\square$