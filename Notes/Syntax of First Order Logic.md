---
tags:
  - Note
---
202309211509

Tags : [[Logic]]

---
# Syntax of First Order Logic

## Syntax
### First Order Languages
To define the formulas of [[First Order Logic]] we first fix the underlying Language. A **First Order Language** is a triple $L= (R,F,C)$ where
- $R$ is a countable set of _Relation Symbols_
- $F$ is a countable set of _Function Symbols_
- $C$ is a countable set of _Constants_
We also have a countable set $Var$ of variables.

### Terms
We now build terms, that would then be connected to give formulas.
The set of **Terms** over a **First Order Language** $L$ is the smallest set satisfying the following condition.
- Every constant $c\in C$ is a term
- Every variable $x\in Var$ is a term
- Let $t_{1},t_{2}\dots,t_{n}$ be terms over $L$ and let $f\in F$ be a function symbol of arity $n$. Then $f(t_{1},t_{2}\dots t_{n})$ is a term.
A term which does not contain any variables is called _closed_.

### Atomic Formulas
The atomic formulas of $L$ are defined as follows.
- Let $r\in R$ be a relation symbol and $t_{1}\dots t_{n}$ are terms over $L$ then $r(t_{1},\dots t_{n})$ is an atomic formula
- Let $t_1$ and $t_{2}$ be terms, then $t_{1}\equiv t_{2}$ is an atomic formulas

### Formulas
Given the above set of atomic formulas, we can define the complete set of formulas $\Phi_{L}$ is the following way.
- Every atomic formula over $L$ belongs to $\Phi_{L}$
- If $\varphi\in \Phi_{L}$ then $\lnot\varphi\in\Phi_{L}$
- If $\varphi,\psi\in\Phi_{L}$ then $\varphi\lor\psi\in\Phi_L$
- If $\varphi\in\Phi_{L}$ and $x\in Vars$, then $\exists x\ \varphi\in\Phi_{L}$ 
And we use parentheses to disambiguate the formula.

```ad-info
The *Terms* and things related to it all, live inside the universe, Hence symbols from $F$ are only used in terms. The *Formulas* are to be interpreted as true of false statements. 
```

---
# References
[[First Order Logic]]
[[Semantics of First Order Logic]]