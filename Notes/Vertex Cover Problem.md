---
tags:
  - Note
---
202309281809

Tags : [[Advanced Algorithms]]

---
# Vertex Cover Problem

**Given:** Graph $G=(V,E)$
**Goal:** If $S\subset V$ is s.t. every edge has at least one endpoint in $S$, it is called a *Vertex Cover*. Minimise $|S|$.

```ad-success
title: Idea: Lower Bounds
1. Find a lower bound (efficiently computable).
2. $A(I)\le\alpha.LB(I)\le\alpha.OPT(I)$.
```

$OPT\ge$ size of any matching
**Algorithm:** Take a maximal matching, and pick both endpoints and add them to $S$.
**Analysis:** $A\le2.\text{(size of a matching)}\le2.OPT$.
Thus we get a $2-$approximation.

---
## Natural questions

- Can we get a $(>2)-$approximation using the same algorithm and the same LB? (Can the analysis be improved?)
*Answer:* No. Consider $K_{n,n}$. Max $VC=n$, max matching $=n$.
Our solution will have cost $2n$, which means our analysis is tight.
- Can a different algorithm give a better approximation using the same LB?
*Answer:* No. $K_{n}$, $n$ odd has $OPT=n-1$, max matching $=\frac{n-1}{2}$.
- Can we improve the approx ratio beyond $2$ using a different LB?
*Answer:* Open

---
# References
[[Approximation Algorithms]]