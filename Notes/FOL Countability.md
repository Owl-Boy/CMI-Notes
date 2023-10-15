---
tags:
  - Note
  - Incomplete
---
202310131210

Tags : [[Logic]]

---
# FOL Countability
Suppose $X$ is a set of formulas that is satisfiable. If the logical language is countable (countably many constants), then $X$ has a (at most) countable model, i.e. (there is a countable universe in which $X$ is satisfied).

**Proof:** Suppose $\mathcal{I}\vDash X$. Then $X\cup\phi_{Eq}\cup\phi_{Q}\cup\phi_{H}$ is propositionally satisfiable. So $X\cup\phi_{Eq}\cup\phi_{Q}\cup\phi_{H}$ is satisfiable in a countable model.

```ad-info
title:
As a result of above, we can't define the set of real numbers in FOL using countably many constants.(??)
```

---
## Lowenheim-Skolem theorem
If a set $X$ of formulas has finite models of arbitrary size, then it also has a (at least) countable model.

**Proof:** Let $\lambda_{n}$ be the formula $\lambda_{n} = \exists x_{1}\dots x_{n}\bigwedge\limits_{\substack{i\neq j\\ i,j\in\{1,\dots,n\}}}x_{i}\neq x_{j}$
$Y=X\cup\{\lambda_{n}|n\ge 1\}$
$Y_{f}= X'\cup\{\lambda_{i},\lambda_{j},\dots,\lambda_{N}\}$ (??)
$\mathcal{I}\vDash Y$
($Y$ has to be at least countable because any model that satisfies $Y$ and is finite will satisfy only up to some $\lambda_{n}$, it will not satisfy $\lambda_{n+1}$.) (??)

---
## Upward LS theorem
Suppose $X$ has an infinite model. Then for every set $A$, $X$ has a model whose cardinality is at least that of $A$.

**Proof:** $C=\{c_{a}|a\in A\}$
$Y=X\cup\{\lnot(c_{a}=c_{b})|a,b\in A,a\neq b\}$
$Y_{f}\subset Y$

---
$G=(V,E)\quad L:R=\{E\}$
There is an edge between $x,y:E(x,y)$
There is a path of length $2$ between $x,y:\exists z\ E(x,z)\land E(z,y)$

Can we have a formula for "There is a path between $x,y$"?
No!
**Proof:** $p_{n}=\exists x_{1}\dots x_{n}\ E(x,x_{1})\land E(x_{1},x_{2})\land\dots\land E(x_{n},y)$
Suppose "Path between $x,y$" is definable, say by the formula $\varphi(x,y)$.
$\varphi_{C}=\forall x\forall y\ \varphi(x,y)$
$q_{n}=\bigwedge\limits_{1\le i\le n}\lnot p_{n}(x,y)$
$X=\{\varphi_{C}\}\cup\{q_{n}|n\ge 1\}$

Now any finite subset of $X$ is satisfiable, but $X$ itself will not be if we take $G$ to be an infinite (say path) graph.(??)

---
What do we do if we want to say this about finite graphs?
Can we say that "Path between $x,y$" is not definable in finite graphs?

Suppose $\mathcal{I}_{1},\mathcal{I}_{2}$ are finite structures that agree on all FO sentences. Then $\mathcal{I}_{1},\mathcal{I}_{2}$ are isomorphic. (We will prove this for graphs for ease, although we can prove this for any structure.)
**Proof:** $G=(V,E)$, $|V|=n$
$\varphi_{G}:\exists x_{1}\dots x_{n}$ "$x_{i},x_{j}$ are pairwise distinct" $\land\bigwedge\limits_{v_{1},v_{2}\in E}E(x_{1},x_{2})\land\bigwedge\limits_{v_{1},v_{2}\not\in E}\lnot E(x_{1},x_{2})$

---
# References
