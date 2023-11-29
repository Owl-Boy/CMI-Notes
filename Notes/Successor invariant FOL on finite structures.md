---
tags:
  - Note
  - Incomplete
---
202311211411

Tags : [[Logic]]
# Successor invariant FOL on finite structures
---
$\sigma:\{ R,F,C\}$, $S\in F$ (successor function which we will call a relation), $\#(S)=1$ (the arity is 1)
A formula $\varphi$ is said to be *successor invariant* on a class of structures $\mathcal{C}$ if for all $\mathcal{M}\in \mathcal{C}$, for all successor relations $S_{1},S_{2}$ on $|\mathcal{M}|$ (why mod??), $\mathcal{M},S_{1}\vDash\varphi$ iff$\mathcal{M},S_{2}\vDash\varphi$.

**Fo-succ inv:** Class of structures (??) that can be defined using the successor relation in FO, and are succ inv.

> [!info] Fo-succ inv $\supsetneq$ FO on finite structures.

> [!info] Fo-succ inv = FO on finite bounded degree structures.
> Finite bounded degree refers to the max degree of an element in the (??) graph, which just counts the number of elements it appears with, together, in some relation.

---
## Order invariant FO
$\in,<$
$(X,\mathcal{P}(X)):$ structures over $\{ \epsilon \}$
$a\in b$ iff $b\in\mathcal{P}(X)$ and $a$ is in $b$.

$\exists y:S_{2}\ \forall x:S_{1}\quad x \not \in y$ (empty set exists)
$\forall x:S_{1}\ \exists y:S_{2}\quad(x \in y \land \forall z:S_{1}\ z\in y \implies z=x)$ (singletons exists for all)$\forall y_{1},y_{2}:S_{2}\ \exists y_{3}:S_{2}\quad(\forall x:S_{1}\ x \in y_{1}\implies x \in y_{3})\land(\forall x:S_{1}\ x \in y_{2}\implies x \in y_{3})\land(\forall x:S_{1}\ x \in y_{3}\implies x \in y_{1}\lor x \in y_{2})$(closed under union)






---
# References
[[First Order Logic]]
[Successor invariant FOL on finite structures, Benjamin, Rossman, Journal of symbolic Logic 2007]