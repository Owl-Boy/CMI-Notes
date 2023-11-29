---
tags:
  - Note
---
202311291611

Tags : [[Logic]]
# Quanitifier Elimination for Natural Numbers with Successor
---
>[!note] Definition
>A theory $T$ admits *quantifier elimination* iff for every formula $\varphi$, there is a quantifier free formula $\psi$ such that 
>$$
>T\models (\varphi \leftrightarrow \psi)
>$$

^411d8b

---
We can assume that every formula $\varphi$ is of the form
$$
\exists x(\alpha_{1}\land \alpha_{2}\dots\alpha_{n})
$$
where each $\alpha_i$ is an atomic formula or negation of one.

We can also assume that each $\alpha_i$ contain $x$ otherwise we have 
$$
\exists x(\alpha \land \beta) \models  =\!\!\!| \alpha \land \exists x \beta
$$
if $\alpha$ does not contain $x$.

---
>[!hint] Idea
>If all of the formulas are negations of equality. Then we always have a solution (the formula discard finitely many options from $\mathbb N$)
>If any of the formulas is not a negation of equality. We replace the variable with the term everywhere and make sure that the term is satisfied by a non-negative value of $x$.
## Negation Elimination
So we have that each $\alpha_i$ has the form $\mathbf{S}^n(x)\equiv \mathbf S^m(u)$ where $u$ us $\mathbf{0}$ or another variable.

If $u=x$ then it is trivial. So we assume that $u\ne x$
Then we have the terms of the following type

### All atomic formulas are negated
$\mathbf{S}^nx\equiv t$ where $t$ does not contain $x$. If every single atomic formula negated. Then we replace it by $\mathbf{0} \equiv \mathbf{0}$

### $\alpha_{0}$ is $\mathbf S^n(x)\equiv t$
The value for $x$ needs to be non-negative, so we replace the other formula by
$$
t\not \equiv \mathbf{0}\land t\not \equiv \mathbf{S}(\mathbf{0})\land\dots \land t\not\equiv \mathbf{S}^{m-1}(\mathbf{0})
$$
if $m>0$ otherwise $\mathbf 0 \equiv \mathbf 0$ 
and for every other $\alpha_j$ of the form $\mathbf S^k x\equiv  u$, we replace it with $\mathbf S^k t \equiv \mathbf S^m u$.

Since we have eliminated $x$, we can get rid of the quantifier.

---
# References
- [[Natural Numbers with Successor]]
- [[Natural Numbers with Successor and Ordering]]
- [[Decidability of Presburger Arithmetic]]