---
tags:
  - Note
---
202310021510

Tags : [[Advanced Algorithms]]
# Travelling Salesman Problem
---

**Given:** $n$ cities $a_1,\dots,a_n$, pairwise, symmetric distances $(a_{i},a_{j})\ge 0\ \forall i,j$
**Goal:** Find a tour that visits all cities and incurs minimum cost (all cities visited exactly once).

```ad-info
title: No approximation for the general case
Take $G$, an instance of $HAM-CYCLE$ problem and get $G'$, by setting the weights of edges of $G$ as $0$, and weights of non edges as $1$. So if there is an $\alpha-$approximation algorithm for TSP on $G'$, then it will output a tour of weight $0$ iff there is a Hamiltonian cycle in $G$.
```

Thus, assume metric property.

> [!info] $\alpha-$approximation of general $TSP \implies$ Hamiltonian cycle $\in P$ where $\alpha\in\text{Poly}(n)$.
> *Proof:* Given any graph $G$, give wt $1$ to $e$ if $e\in E$ and wt $\alpha n$ to $e \not\in E$.


## Algorithm
---
We have the metric property: $d(a_{i},a_{k})\leq d(a_{i},a_{j})+d(a_{j},a_{k})$.
**LB:** Cost of a Minimum Spanning Tree (MST)

1. Find an MST $T$ of $A$.
2. Do a traversal of the MST. (It is okay to traverse an edge twice.)
3. Now reduce the walk to a tour/path so that no edge is traversed twice.
$$
2.OPT\geq 2.MST\geq \text{the resulting path}.
$$
> [!success] Thus we get a $2-$approximation algorithm.

## Christofide's algorithm
---
1. Find an MST $T$.
2. Find a min weight perfect matching $M$ on the odd degree vertices.
3. Find an Eulerian traversal of $T\cup M$.
4. Output a TSP tour by *short cutting* the Eulerian traversal. (Remove repeated vertices.)
**LB1:** $\text{Cost of MST}\leq \text{Cost}(OPT)$
**LB2:** $\text{Cost of min wt perfect matching on any subset }S\subseteq V\leq \frac{1}{2}\text{Cost}(OPT)$
$$
\begin{align*}
\text{Cost(our tour)}&\leq \text{Cost}(T) + \text{Cost}(M)\\
&\leq \frac{3}{2}\text{Cost}(OPT).
\end{align*}
$$
> [!success] Thus we get a $\frac{3}{2}-$approximation algorithm.

---
# References
[[Approximation Algorithms]]
-> [[Job Scheduling Problem]]