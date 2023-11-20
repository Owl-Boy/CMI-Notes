---
tags:
  - Note
  - Incomplete
---
202311141411

Tags : [[Logic]]

---
# Finite Essentially Uninterpreted (FEU) fragment

## Satisfiability Modulo Theories (SMT)
Consider $(\mathbb{N};+;<;0)f,g,p,r$, where the things in the bracket are *'interpreted'* (i.e. they have the general interpretation) and the ones outside are *'uninterpreted'* (i.e. they can be anything, which can later be interpreted). We want to check the satisfiability of $\varphi$ modulo these constraints.
This problem is what is solved by SMT solvers.

## Skolemization
We can trade existential quantified variables for *(Skolem) functions*.
**example**
$$
\varphi:\quad \forall \bar{x}\exists y(\dots r(\dots y \dots)\dots)
$$
means that for every tuple $\bar{x}$ we can find a $y$ that satisfies the formula, This can be represented with the function $f:S^{k}\to S$
and we can rewrite the formula as
$$
\varphi:\quad \forall \bar{x}(\dots r(\dots f(\bar{x})\dots)\dots)
$$
## Essentially uninterpreted formulas
A formula $\varphi$ is essentially uninterpreted if any variable in $\varphi$ appears only as an argument of uninterpreted function or predicate symbols (= relation symbols).
So $f(g(x_{1})+0)\leq h(x_{1})\cup p(f(x_{1})+ b.x_{2})$ is uninterpreted while $x_{1}+f(x_{2})$ is not, because $x_{1}$ is an argument of $'+'$, which is interpreted.

**Conjunctive Normal Form:**
- *Literal:* atomic formula or its negation
- *Clause:* disjunction of literals
- *CNF formula:* conjunction of clauses

**Ground formulas:** formulas that don't use variables

```ad-success
title: Goal
Given a CNF formula $\varphi$, we would like to come up with a Ground formula $\varphi^{*}$ s.t. $\varphi^{*}$ is satisfiable iff $\varphi$ is satisfiable.
```

### Notation




---
# References
