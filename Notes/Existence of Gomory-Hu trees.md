---
tags:
  - Note
  - Incomplete
---
202311031411

Tags : [[Advanced Algorithms]]

# Existence of Gomory-Hu trees
---

**Definition:** $T$ is a *Gomory-Hu tree* for $G$ if:
- $T=(V,F)$, weights $w'\geq 0$, and
- for every $(u,v)\in F$, $w'(u,v)=w(\text{a }u-v\text{ min-cut in }G)$ and $T \setminus \{ (u,v) \}$ is the $u-v$ mincut in $G$.

$E$ is a finite set.
**Submodular function:** $f:2^{E}\to \mathbb{R}$ is said to be a submodular function if $\forall A,B \subset E,$ $f(A)+f(B)\geq f(A\cup B)+f(A\cap B)$.

Alternate definition: $\forall A \subset B,$ $f(A+e)-f(A)\geq f(B+e)-f(B)$.
(Adding an element to a smaller set would make a bigger difference to its value than adding the same element to a larger set.)
Equivalence between the two definitions can be seen easily by letting $X=A\cap B,Y=A,B=X\cup Z$, and the case where $Z$ is singleton gives the second definition.

*Cut:* $W \subseteq V$ is a cut of $G=(V,E)$. $f(W)=\sum\limits_{e\in\delta(W)}w(e)$. Call $f$ the cut function.
```ad-info
title:
**Lemma:** Cut function is submodular.
*Proof:* Let $A$ and $B$ be two cuts. Draw Venn diagram, do arithmetic, bada boom bada bang!
```

```ad-info
title: Useful Fact
Any symmetric submodular function is also posi-modular.
**Posi-modularity:** For cuts $A,B$, $f(A)+f(B)\geq f(A\setminus B)+f(B\setminus A)$. Proof is easy by the previous method, or by using the fact that the function is symmetric (i.e. $f(A)=f(\bar{A})$) . 
```

```ad-important
title:
**Theorem:** Let $W$ be an $s,t$ mincut in $G$. Then $\forall u,v\in W$ there is a $(u-v)$ mincut $X$ s.t. $X \subseteq W$.
*Proof:* Let $X$ be a $(u,v)$ mincut but $X\not\subseteq W$.

Case I: $t\not\in X$.
$f(X)+f(W)\geq f(X\cup W)+f(X\cap W)$
$X\cup W: (s,t)$ cut, $X\cap W: (u,v)$ cut
$f(X)\leq f(X\cap W)$, $f(W)\leq f(X\cup W)$
$\implies f(X)=f(X\cap W)$. Thus $X\cap W$ is also a $(u-v)$ mincut.

Case II: $t\in X$.
$f(W)+f(X)\geq f(X\setminus W)+f(W\setminus X)$
$W\setminus X:(u,v)$ cut
$X\setminus W:(s,t)$ cut
$\implies W\setminus X$ is also a $(u,v)$ mincut.
```

---
# References
