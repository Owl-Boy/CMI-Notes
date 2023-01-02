202212152212

Type : #Note
Tags : [[PLC]]

---
# Partial Functions

```ad-note
title:
A _Partial Function_ is a function that has values on some arguments but not on all arguments
```
The reason why a function would not return all values are :
- _Error Termination:_ Evaluation of a function cannot proceed because of a conflict between the operator and an operand.
- _Nontermination:_ Evaluation of a function proceeds indefinitely.
An example of the first case would be the expression `x:= 3 / 0`, because devision by `0` is undefined.
An example of the second scenario can be a function `f(x: int) := if x = 0 then 0 else x + f(x-2)`, this function does not terminate when `3` is given as an argument.

A partial function is __not__ a function as defined by the mathematical sense. 
A mathematical function $f:A\to B$ is a set of ordered pair $f\subset A\times B$ satisfying the following conditions:
1. If $(x, y) \in f$ and $(x, z) \in f$, then $y =z$.
2. For every $x \in A$, there exists a $y\in B$ such that $(x,y) \in f$.
But a partial function only follows the first condition.



---
# Related Problems

---
# References
