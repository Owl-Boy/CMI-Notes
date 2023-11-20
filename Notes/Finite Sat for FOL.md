---
tags:
  - Note
  - Incomplete
---
202310101410

Tags : [[Logic]]

---
# Finite Sat for FOL
If a set $X$ of FO formulas is finitely satisfiable, then $X$ is satisfiable.

**Proof:** (FOL Sat $\implies$ prop Sat)
(Prop Sat $\implies$ FOL Sat)
...

1. $\{x_{1}\equiv x_{2},x_{2}\equiv x_{3},x_{3}\not\equiv x_{1}\}$.
Simply replacing each formula with an atomic proposition doesn't work because we lose information about the relations between the formulas.
$\{p_{12},p_{23},p_{31},p_{12}\land p_{23}\implies\lnot p_{31}\}$, however, works!

2. $\{\forall x(r(x)\implies s(x)),\forall x (r(x)),\exists x (\lnot s(x))\}$
The previous way shouldn't work because it's not as straightforward to see that two of these formulas imply that the third should be negated. (In fact it only works for $\equiv$ and $\exists$.)
If we were to try proving that, it would be equivalent to finding whether this set is satisfiable in FOL itself, which defeats the purpose.

**Prime formulas:** formulas of the form $t_{1}\equiv t_{2}, r(t_{1},\dots,t_{n}),\text{ or }\exists x\ \varphi$.
$\{\lnot\exists x\ (r(x)\land s(x)),\lnot\exists x\ \lnot r(x),\exists x\ \lnot s(x)\}$

- $p_{1}:\exists x\ (r(x)\land\lnot s(x))$,
- $p_{2}:\exists x\ \lnot r(x)$,
- $p_{3}:\exists x\ \lnot s(x)$

$\{\lnot p_{1},\lnot p_{2},p_{3}\}$

**Prime formula structure:** For FO language $L$, let $\mathcal{P}_{L}$ be the set of all prime formulas.

---

**Lemma:** Let $\mathcal{I}$ be an interpretation. There exists a valuation $v:\mathcal{P}_{L}\to\{\top,\bot\}$ s.t. for FO formula $\varphi$, $\mathcal{I}\models_{FO}\varphi$ iff $v\models_{\mathcal{P}_L}\varphi$.
(All this lemma is saying is that we can make up a valuation. The valuation loses a lot of information that the interpretation has, so the *converse is not true.*)

- Equality is transitive.
- Suppose $\exists x\ \varphi(x)$ is true. There is a term $t_{\varphi}$ which certifies this. We add $\exists x\ \varphi(x)\implies\varphi(t_{\varphi})$.
- Suppose $\lnot\exists x\ \varphi(x)$ is true. Every element satisfies $\lnot\varphi$. We add $\lnot\ \exists x\ \varphi(x)\implies\lnot\varphi(t)$ for an arbitrary term $t$.

---
# References
[[First Order Logic]]
[[Finite Sat for FOL Motivation]]