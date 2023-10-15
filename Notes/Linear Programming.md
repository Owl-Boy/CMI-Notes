---
tags:
  - Note
---

Tags : [[Advanced Algorithms]]

---
# Linear Programming
Linear objective function: Minimise $c_1x_1 + \dots + c_nx_n = c^Tx$ subject to
linear constraints:
    $a_{11}x_1 + \dots a_{1n}x_n \geq b_1$
    .
    .
    .
    $a_{m1}x_1 + \dots a_{mn}x_n \geq b_m$
    $x_i \geq 0$

Variables: $x_i$
Every solution $x$ is a point in $\mathbb{R}^n$.

## Properties
- The feasible region is a convex polyhedron in $\mathbb{R}^n$.
- The optimum is always attained at a vertex/extreme point of the feasible region.
- Linear programs can be solved in polytime.

---
# References
[[Integrality Gap]]
[[(Weighted) Vertex Cover using LP]]
[[Uncapacitated Facility location]]