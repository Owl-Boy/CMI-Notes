---
tags:
  - Note
---
202309211209

Tags : [[Advanced Algorithms]]

---
# (Weighted) Vertex Cover using LP

## Vertex Cover

$|V| = n$
$|E| = m$

Variables: $x_1, \dots , x_n$
$$
x_{i}=\left\{
\begin{align*}
1 &&\text{iff } v_{i}\in S\\
0 &&\text{otherwise.}

\end{align*}
\right.
$$
$\sum_{i=1}^n x_i = |S|$.

Minimise $|S|$, wrt constraints:
- $x_i + x_j \geq 1 \quad\forall (v_i, v_j) \in E$
- $\begin{align*}x_i \in \{0,1\} \quad\forall v_i \in E&&(@)\end{align*}$
@ makes the problem NP hard, so we sacrifice the integrality constraint, and just require the variables to be non negative. (We don't need $x_i \leq 1$ constraint because the program will anyway minimise $|S|$.)
We then use [[(Weighted) Vertex Cover using LP#Rounding|rounding]] techniques to get an actual solution.

---

## Weighted Vertex Cover

Graph $G$, each vertex $v_i \in V$ has a weight $w_i \geq 0$.
Find a vertex cover of minimum weight.

```ad-todo
title: Check
The approx algo based on matchings will not give a 2-approx.
```

Minimise $\sum_{i=1}^n w_ix_i$ (weight of the vertex cover) wrt:
- $x_i + x_j \geq 1 \quad\forall (v_i, v_j) \in E$
- $x_i \geq 0 \quad\forall v_i \in E.$

Opt solution of LP: $x^* = {x^*_1, x^*_2, \cdots , x^*_n}$
For any edge ($v_i,v_j$), $x_i^* + x_j^* \geq 1$
At least one of $x_i^*, x_j^* \geq 1/2$

---
### Rounding
$\{x_i^*\}_{i = 1, \cdots , n}$, fractional
- Construct integral solution $x'$.
- Set $x'_i = 1$ iff $x_i^* \geq 1/2$,
otherwise set $x'_i = 0$.

Rounded integral solution $x' = {x'_i}$.

```ad-info
title:
**Claim:** $x'$ is a valid vertex cover.
```

For each $i$, $x'_i \leq 2x_i^*$.
$\sum_{i=1}^n w_i x'_i \leq 2\sum_{i=1}^n w_i x_i^* = 2.OPT(LP).$

$OPT(LP) \leq OPT(ILP).$

---
# References
[[Integrality Gap]]
[[Linear Programming]]