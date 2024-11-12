---
tags:
  - Note
  - Incomplete
aliases:
  - L
---
202411101511

Tags : [[Set Theory]]
# Constructable Sets
---
We will now construct the class $L$ of *constructible sets* in $\text{ZF}$ which is a model of $\text{ZFC+GCH}$.

We use a [[Definable Power Set]] function, similar to the $\mathcal P$, powerset function, and define a notion analogous to rank of a set, and use that to construct the class.

>[!definition]
>By transfinite recursion define $L(\alpha)$ for $\alpha \in \mathbf{ON}$ by:
>- $L(0)=0$
>- $L(\alpha+1)=\mathcal D(L(\alpha))$
>- $L(\alpha)= \bigcup_{\xi<\alpha}L(\xi)$ when $\alpha$ is a limit ordinal

And using these classes we can construct the following

>[!definition]
>$\mathbf{L}= \bigcup \{ L(\alpha): \alpha \in \mathbf{ON} \}$

>[!theorem] Lemma
>For each $\alpha$:
>1. $L(\alpha)$ is transitive.
>2. $\forall \xi \leq \alpha(L(\xi) \subseteq L(\alpha))$

---
# References
[[L is a model of ZF]]
[[Definable Power Set]]
