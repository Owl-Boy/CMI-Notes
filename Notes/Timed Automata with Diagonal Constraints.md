---
tags:
  - Note
---
202310282010

Tags : [[Timed Automata]]


# Timed Automata with Diagonal Constraints
---

>[!note] Definition
>A *timed automata* with *diagonal constraints* is a normal *timed automata* whose guards come from the set defined below. I will also call them *d-timed automata*.

## Diagonal Constraints
let $X$ be a set of clocks. The set of *guards with diagonal constraints* $\Phi(X)$ is given the following grammar:
$$
\Phi(X)\quad:=\quad x \diamond c \; |\;x-y\diamond c\;|\; \Phi(X) \land\Phi(X) 
$$
where $x, y\in X$ and $\diamond : \{\le, <, =, >, \geq\}$ and $c \in Z$ 

---

There are two main theorem for *d-timed automata*
- Diagonal Constraints do not add any power. That is because there is a [[D-Timed Automata to Timed Automata Construction|construction]] from a *d-timed automata* of *timed automata*.
- [[Diagonal Constraints Offer Exponential Succinctness.]]



---
# References
- [Srivathsan's Notes](https://www.cmi.ac.in/~sri/Courses/TA/Slides/Diagonal-notes.pdf)