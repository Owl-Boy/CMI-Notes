---
tags:
  - Note
  - Incomplete
---
202309300009

Tags : [[Logic]]

---
# Satisfiability in First Order Logic
```ad-question
title: Goal
When do we know if set $X\subseteq\Phi_{L}$ of sentences in a [[Syntax of First Order Logic#First Order Languages|First Order Language]] have a corresponding [[Semantics of First Order Logic#First Order Structures|First Order Structure]] $\mathcal M$ such that for each $\varphi\in X,\mathcal M\models\varphi$.
In other words, when do we say that a set is *Satisfiable*.
```

Henkin's Solution to the question reduces the question of [[Satisfiability in Propositional Logic]]

```ad-failure
title: Approaches that do not work
Just replacing all the Formulas that cannot be modeled with propositional logic using new propositional variables does not directly work.

For example
$$
\exists x\ r(x)\land\forall x\ r'(x) 
$$
where $r'$ is defined to be $\lnot r$

Here putting two different propositional variables in case of the two quantified terms gives a sentence that is satisfiable, even though the First Order Sentence is clearly.
```

Henkin's approach is to keep expanding the language by adding more constants to it to eventually replace the quantified formulas. This will also blow up the size of $X$ because we need to check for more formulas, but then we would be able to use **Propositional Satisfiability** Instead.

---
# References
