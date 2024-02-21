---
tags:
  - Note
  - Incomplete
---
202402021402

Tags : [[Combinatorial Optimisation]]
# LP algorithm for general Perfect Matching
---
$G=(V,E)$.
$|V|=n$ (even), $|E|=m$.
$\delta(v)=$ set of edges incident on $v$,
$\delta(S)=$ set of edges with exactly one endpoint in $S$.
### LP:
- $\sum\limits_{e\in\delta(v)}x_{e}=1\quad \forall v\in V$
- $\sum\limits_{e\in\delta(S)}x_{e}\geq1\quad \forall S\subseteq V,|S|\text{ is odd}, 3\leq |S|< |V|-1$
- $x_{e}\geq 0\quad \forall e \in E$

> [!note] The second constraint here says that for every odd subset, not everything is matched within itself, like in the triangle $\frac{1}{2}, \frac{1}{2}, \frac{1}{2}$ case. We require at least one edge in the boundary of each odd set to be in the matching (and relax integrality).

Let $P_{G}$ be the polytope of graph $G$ given by the above LP.

**Obs.:**
1. Any $0/1$ point in $P_{G}$ is a perfect matching of $G$.
2. All perfect matchings of $G$ are in $P$.

---

**Theorem:** Vertices of $P$ are perfect matchings of $G$, i.e. $P=$ convex hull of the perfect matchings.

*Proof:* Suppose not.
There is a graph $G$, and an extreme point $\hat{x}$ of the polytope $P_{G}$ which is not a perfect matching of $G$. Among all such counterexamples, let $G$ be one with minimum $|V|+|E|$.

*Claim 1:* $\forall e\in E\quad 0<\hat{x_{e}}<1$.
1. If $\hat{x}_{e_{i}}=0$, then $G\setminus \{ e_{i} \}$ is a smaller counterexample.
2. If $\hat{x}_{e_{i}}=1,\ e_{i}=(u,v)$, then $G\setminus \{ u,v \}$ is a smaller counterexample.

(Check that the new $\hat{x}\setminus e_{i}$ is still an extreme point of the new polytope, in 2. as well.)

*Obs.:* 
1. $G$ has no degree $1$ vertex.
2. $G$ can't have all vertices of degree $2$, because then $G$ would just be a bunch of vertex disjoint cycles. If all the cycles are even, we get a perfect bipartite matching, and if any of them are odd, then there does not exist a perfect matching at all and the polytope itself is empty!

So $G$ has  a vertex of degree $>2$. Which means $|E|>|V|$, or $m>n$.

$\hat{x}\in\mathbb{R}^{m}$ is a vertex (extreme point) of $P_{G}$, so $m$ constraints must be tight at $\hat{x}$.
There must be at least one of the second type constraints which is tight at $\hat{x}$. Say it is due to the set $U\subseteq V$.

*Goal:* To show $\hat{y},\hat{z}$ s.t. $\hat{x}=\lambda \hat{y}+(1-\lambda)\hat{z}$.

We know that $\hat{x}_{e_{1}}+\dots+\hat{x}_{e_{h}}=1$, where $e_{1},\dots,e_{h}$ are the edges that go from $U$ to $V\setminus U=\bar{U}$.
Shrink $U$ to a new vertex $u$ to get a smaller graph $G'$, and similarly $\bar{U}$ to $\bar{u}$ to get $G''$.

*Obs.:*
1. A perfect matching $M$ of $G$ is a valid perfect matching $M'$ of $G'$, and $M''$ of $G''$ iff $|M\cap \{ e_{1},\dots,e_{h} \}|=1$.
2. If $M'$ and $M''$ are perfect matchings of $G'$, $G''$ respectively, using the same edge among $e_{1},\dots,e_{h}$, then $M'\cup M''$ is a perfect matching for $G$.

Since $G'$ and $G''$ are smaller than $G$, they obey the theorem, i.e. their polytopes are integral.
$\hat{x}_{G'}=\sum\limits_{i=1}^{k_{1}}\alpha_{i}M'_{i}$.
$\hat{x}_{G''}=\sum\limits_{j=1}^{k_{2}}\beta_{i}M''_{j}$.
$\sum \alpha_{i}=\sum \beta_{j}=1$, $0\leq\alpha_{i}\leq 1$, $0\leq\beta_{i}\leq 1$.

$\hat{x}_{e_{1}}=\sum\limits_{i:e_{1}\in M'_{i}}\alpha_{i}=\sum\limits_{j:e_{1}\in M''_{j}}\beta_{j}$

For each edge $e_{k}$, take $\sum\limits_{i: e_{k}\in M'_{i}}\alpha_{i}\sum\limits_{j: e_{k}\in M''_{j}}\beta_{j}(M'_{i}\cup M''_{j})$ , scale it by the right thing to write $\hat{x}_{G}$ as the convex combination of these "union matchings".






---
# References
