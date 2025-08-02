title: Finitely Generated Modules over Noetherian Rings are Finitely Presented
description: A concise proof that every finitely generated module over a Noetherian ring admits a finite presentation.

---

**Definition.**
A ring $R$ is **_Noetherian_** if every ideal of $R$ is finitely generated.

**Definition.**
An $R$-module $M$ is **_finitely generated_** if there exists a surjection $R^{\oplus n} \twoheadrightarrow M$ for some $n\in\mathbb N$.

**Definition.**
An $R$-module $M$ is **_finitely presented_** if there is an exact sequence

$$
R^{\oplus m}\longrightarrow R^{\oplus n}\longrightarrow M\longrightarrow 0
$$

with $m,n\in\mathbb N$.

**Theorem.**
If $R$ is a Noetherian ring and $M$ is a finitely generated $R$-module, then $M$ is finitely presented.

_Proof._
Let $\varphi: R^{\oplus n} \twoheadrightarrow M$ be a surjection defining the finite generation of $M$. As $R$ is a Noetherian ring, the free module $R^{\oplus n}$ is a Noetherian module. The kernel, $K = \operatorname{ker}(\varphi)$, is a submodule of $R^{\oplus n}$ and is therefore finitely generated. Let $\psi: R^{\oplus m} \to R^{\oplus n}$ be a homomorphism whose image is $K$. The sequence

$$
R^{\oplus m}\xrightarrow{\psi}R^{\oplus n}\xrightarrow{\varphi}M\longrightarrow 0
$$

is exact, providing a finite presentation for $M$. $\square$
