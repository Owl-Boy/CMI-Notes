---
tags:
  - Note
  - Incomplete
---
202310131210

Tags : [[Logic]]

# FOL Inexpressibility
---
We get that we can't define the set of Real numbers in FO using countably many constants due to [[Löwenheim-Skolem and its Variants|Löwenheim-Skolem Theorem]].

## Connectivity of arbitrary graphs is not FO-definable
---
$G=(V,E)\quad L:R=\{E\}$
There is an edge between $x,y:E(x,y)$
There is a path of length $2$ between $x,y:\exists z\ E(x,z)\land E(z,y)$

>[!question] Can we have a formula for "There is a path between $x,y$"?
>No!

**Proof:** $p_{n}=\exists x_{1}\dots x_{n}\ E(x,x_{1})\land E(x_{1},x_{2})\land\dots\land E(x_{n},y)$
Suppose "Path between $x,y$" is definable, say by the formula $\varphi(x,y)$.
$\varphi_{C}=\forall x\forall y\ \varphi(x,y)$
$q_{n}=\bigwedge\limits_{1\le i\le n}\lnot p_{n}(x,y)$
$X=\{\varphi_{C}\}\cup\{q_{n}|n\ge 1\}$

Now any finite subset of $X$ is satisfiable, but $X$ itself will not be if we take $G$ to be an infinite (say path) graph.

---
What do we do if we want to say this about finite graphs?

> [!question] Can we say that "Path between $x,y$" is not definable in finite graphs?
> We can probably try compactness?

Surprise! It doesn't work.

There is a set of formulas $X$ such that $X$ has no finite models, and every finite subset of $X$ has a finite model.
**Proof:** Let $\lambda_{n}$ be the formula $\lambda_{n} = \exists x_{1}\dots x_{n}\bigwedge\limits_{\substack{i\neq j\\ i,j\in\{1,\dots,n\}}}x_{i}\not\equiv x_{j}$
($\lambda_{n}$ just says that there are at least $n$ distinct elements in the universe.)
$X=\{\lambda_{n}|n\ge 1\}$. Clearly $X$ has no finite model, but for each finite subset $\{\lambda_{n_{1}},\dots,\lambda_{n_{k}}\}$ of $X$, a set with cardinality greater than all the $n_{i}$'s is a model.

---
## Uncategorised stuff motivating quantifier rank

Suppose $\mathcal{I}_{1},\mathcal{I}_{2}$ are finite structures that agree on all FO sentences. Then $\mathcal{I}_{1},\mathcal{I}_{2}$ are isomorphic. (We will prove this for graphs for ease, although we can prove this for any structure.)
(This also gives us that given any graph $G$, we can define an FO structure that models it, up to isomorphism.)
**Proof:** $G=(V,E)$, $|V|=n$
$\varphi_{G}:\exists x_{1}\dots x_{n}$ "$x_{i},x_{j}$ are pairwise distinct" $\land\bigwedge\limits_{v_{1},v_{2}\in E}E(x_{1},x_{2})\land\bigwedge\limits_{v_{1},v_{2}\not\in E}\lnot E(x_{1},x_{2})$

smth

---
For a bigger graph our nesting is deeper. Is it required intrinsically by the graph itself? If so, can we use the *depth* or *complexity* of the nesting to say something like "If you can only go this deep then you can't distinguish between graphs of *complexity* more than that".
This is what we'll call the [[Complexity of an FO formula|quantifier rank]] of the FO formula.

---
# References
[[Löwenheim-Skolem and its Variants]]
[[First Order Logic]]