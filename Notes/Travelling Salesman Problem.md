---
tags:
  - Note
  - Incomplete
---
202310021510

Tags : [[Advanced Algorithms]]

---
# Travelling Salesman Problem

**Given:** $n$ cities $a_1,\dots,a_n$, pairwise distances $(a_{i},a_{j})\ge 0\ \forall i,j$
**Goal:** Find a tour that visits all cities and incurs min cost (all cities visited exactly once).

```ad-info
title: No approximation for the general case
Take $G$, and assume all weights of edges of $G$ are of cost $1$ and cost of non edges is $k$ for $k$ as large as desired.
Thus, assume metric property.
```

$\alpha-$approximation of general $TSP \implies$ Hamiltonian cycle $\in P$ where $\alpha\in\text{Poly}(n)$.


---
# References
