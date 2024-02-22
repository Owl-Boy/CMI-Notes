---
tags:
  - Note
  - Incomplete
---
202401121401

Tags : [[Combinatorial Optimisation]]
# LP algorithm for Bipartite Matching
---
$$
x_{e}=\left\{
\begin{align*}
1 &&\text{iff } e\in M\\
0 &&\text{otherwise.}

\end{align*}
\right.
$$
$\max\sum\limits_{e \in E}x_{e}$ s.t.:
- $\forall u \in A\cup B,\ \sum\limits_{e\sim v}x_{e}\leq 1$
- $x_{e}\geq 0,\quad\forall e \in E$.

**Obs:** Every matching of $G$ is a feasible point in $P \in\mathbb{R}^{m}$.
$\mathcal{M}:$ convex hull of matchings in $G$

**Theorem:** $P=\mathcal{M}$
Feasible region of this LP = Convex hull of all matchings in $G$ in any bipartite graph $G$.
*Idea:* Take a feasible, fractional point. Show that it can be expressed as a convex combination of two points.

---
paper written stuff

---






---
# References
[[Matching Problem]]
[[Linear Programming]]