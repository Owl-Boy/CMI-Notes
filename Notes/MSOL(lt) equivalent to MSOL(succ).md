---
tags:
  - Example
---

202402121216

tags : [[Logic]], [[Automata Theory]]

#  MSOL\[lt] equivalent to MSOL\[succ]
---
>[!Theorem]
>$\text{MSOL}[<]$ is as powerful as $\text{MSOL}[\text{succ}]$.

We can prove that by showing that we can define each function using the other.

- Using $[<]$ to define $[\text{succ}]$.
	- $\text{succ(x, y)} := x<y \land\lnot(\exists z. x < z \land z < y)$
- Using $[\text{succ}]$ to define $[<]$.
	- $x < y\; :=\;\forall X.x \in X \land(\forall a. a \in X \implies \text{succ}(a)\in X)\implies y\in X$

This proves that both additions to $\text{MSOL}$ are equally powerful.

---
# Related
