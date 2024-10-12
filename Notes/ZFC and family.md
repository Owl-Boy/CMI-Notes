---
tags:
  - Note
---
202408101408

Tags : [[Set Theory]]
# ZFC and family
---
- *Extensionality*
	- $\forall z (z\in x \leftrightarrow z \in y) \to x = y$
- *Foundation* ^df7c78
	- $\exists y(y \in x) \to \exists y(y \in x \land \lnot \exists z (z \in x \land z \in y))$
- *Comprehension Scheme* : For each formula $\phi$ which does not have $y$ as free
	- $\exists y \forall x (x \in y \leftrightarrow x \in v \land \phi(x))$
- *Pairing*
	- $\exists z(x \in z \land y \in z)$
- *Union*
	- $\exists A, \forall Y \forall x(x \in Y \land Y \in F \to x \in A)$
- *Replacement Scheme* ^c2b9a6
	- $\forall x \in A \exists ! y \varphi(x, y) \to \exists B \forall x \in A \exists y \in B \varphi(x, y)$
- *Infintiy*
	- $\exists x( \emptyset \in x \land \forall y \in x(S(y) \in x))$
- *Power Set* ^44e52f
	- $\exists y \forall z(z \subseteq x \to z \in y)$
- *Choice*
	- $\emptyset \not\in F \land \forall x \in F \forall y \in F (x \neq y \to x \cap y = \emptyset) \to \exists C \forall x \in F(\text{Sing}(C \cap x))$

1. *ZFC* = all 9 axioms
2. *ZF* = first 8 axioms
3. *ZC* and *Z* are *ZFC* and *ZF* with replacement scheme deleted
4. *X-* is *X* with foundation axiom deleted\
5. *X-P* is *X* with power set axiom deleted
6. *X - Inf* is *X* with infinity axiom deleted


---
# References
