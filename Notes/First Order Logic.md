---
tags:
  - Note
---
202309211409

Tags : [[Logic]]

---
# First Order Logic
```ad-tip
title: Motivation
Consider the typical structures in Maths and CS. Groups, Rings, Monoids etc etc. All of them are sets, equipped with _functions_ and _relations_ on them and sometimes they have _special promoted terms_, like units in groups.

**First Order Logic** gives a natural frameword to talk about these thingies.
The idea is to fix symbols to denote functions, relations and constants and combine the with the standard $\lnot$ and $\lor$ operator. In addtion to all that we have operators to quantify over all elements $\exists$ and $\forall$, and a $\equiv$ operator to check equality of primitive constructs.
```

The [[Syntax of First Order Logic|syntax]] and [[Semantics of First Order Logic|semantics]] are a bit more involved for first order logic, than in _Propositional Logic_.

*Groups* are a really good example to get introduced to first order logic

A Group is a structure $(G,+,0)$ where $G$ is a set, $+$ is a binary operation on it, a special element $0$ and the following properties hold:
- $+$ is associative
- $0$ is the right identity for the operation $+$
- For every element in $G$, it has a right inverse, such applying the operator on those two elements will yield $0$

To formalize this we have the following statements in **First Order Logic** where $op$ represents the operator and $\epsilon$ represents the identity.
- $\forall x\ \forall y\ \forall z\  op(op(x,y),z)\equiv op(x,op(y,z))$
- $\forall x\ op(x,\epsilon)\equiv x$
- $\forall x\exists y\ op(x, y)\equiv \epsilon$

To give this meaning, we fix a set $S$ which is the set we are working with, make $op$ a binary relation on the set, $\equiv$ equivalence on it and $\epsilon$ an element from $S$ which is treated in a special way. so $S$ is the same as the set $G$, $op$ represents $+$ and $\epsilon$ is the identity here.

```ad-success
title:Goal
The goal of first order logic is to capture the properties of mathematical structures.
```

```ad-todo
Revisit Groups after finishing First Order Logic Syntax and Semantics
```

---
# References
