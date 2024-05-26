---
tags:
  - Note
  - Incomplete
---
202403221203

Tags : [[Complexity Theory]]
# Bipartite Graph Perfect Matching
---
$G=((A,B),E)$, $|A|=|B|=n$
**Goal:** To determine whether there exists a perfect matching.

---
stuff written in paper notes:
Proof using the Lovasz matrix of the graph to get the determinant as a polynomial, and then using the Schwarz-Zippel lemma
...
For Lovasz test, we can choose $S=\{ 1,2,\dots,2n \}$.
Randomly pick $x_{ij}\leftarrow a_{ij}\in_{R}S$, $\forall u_{i}v_{j}\in E$.
$\det(\{ a_{ij} \})\neq 0$ with probability $\geq \frac{1}{2}$ iff $G$ has a perfect matching.
$|\det(\{ a_{ij} \})|\leq n!(2n)^{n}\leq n^{4n}$.
So number of primes less than $n^{3}$, is around $\frac{n^{3}}{3\log n}>n^{2}$.












---
# References
