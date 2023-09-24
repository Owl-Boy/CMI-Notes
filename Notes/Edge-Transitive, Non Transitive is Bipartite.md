202308140243

type : #Example
tags : [[Algebraic Graph Theory]]

#  Edge-Transitive, Non Transitive is Bipartite
---
### Theorem:
Let $T$ on a connected graph $G$, be edge transitive bit not vertex transitive. Then $G$ is Bipartite
###  Proof:
Let $X$ and $Y$ be two distinct orbits that share an edge (say $e$)
We know that two such distinct orbits exist because the graph is not vertex transitive, hence $\exists x,y$ such that orbit of $x$ and $y$ are distinct, take $y$ to have share an edge with $X$.

If $X\sqcup Y\ne V$ then consider $z\notin X\sqcup Y$, but since $G$ is edge transitive, take make $e$ incident of $z$, but that implies $z\in X$ or $z\in Y$ which is a contradiction. Thus $X\sqcup Y=V$

Consider $e'=x_{1},x_{2}$
then there exists an automorphism $\alpha$ such that $\alpha(e')=e$. But this is a contradiction as $x_1$ or $x_{2}$ cannot go to $Y$. Hence $e'$ does not exist, hence the graph is bipartite.

---
# Related


