---
tags:
  - Note
  - Incomplete
---
202401311401

Tags : [[Combinatorial Optimisation]]
# Total Unimodularity
---
> [!info] Definition:
> A matrix $A$ is TUM is every square submatrix of $A$ has determinant $0$ or $\pm 1$.

*Observation:* All entries of $A$ are $0$ or $\pm 1$.

$\max c^{T}$ s.t. $Ax\leq b$.
$\{ Ax\leq b \}$ is the polytope $P$.
$n$ variables, $m$ constraints

A polytope $P$ is said to be integral (for our context) if all vertices of $P \in\mathbb{Z}^{n}$. In general we can define a polytope to be integral even if it doesn't have vertices. In that case we just define a polytope to be integral if each face has an integral point.

**Theorem:** If $A$ is TUM then, for each integral vector $b$, the polytope $P$ is integral.
*Proof:* For any vertex $v$ of $P$, there exists a set of $n$ linearly independent constraints given by submatrix $A'_{n\times n}$ of $A$ s.t. $A'v=b$.
$A'$ must be invertible.
$v=A'^{-1}b$.
But $A'^{-1}= \frac{1}{\det(A')}Adj(A')$.

So $A'^{-1}$ is TUM and hence $v$ is integral.

$A$ is TUM $\iff$ $A^{T}$ is TUM.
Dual: $\min y^{T}b$ s.t. $A^{T}y\geq c$.

---
Consider the bipartite matching LP.
$A_{n\times m}$ is the edge incidence matrix which has vertices along the rows and edges along the columns.
**Claim:** $A$ is TUM.
*Proof:* By induction on the size of the submatrix.
Base case is fine.
Assume TUM for all sub-matrices up to size $(k-1)\times(k-1)$.
Let $A'$ be a $k\times k$ submatrix.
- If any row or column of $A'$ is $0$ then $\det(A')=0$.
- If a row or column of $A'$ has only one $1$, then expand along it: $\det(A')=\pm\det(A'')$.
- Otherwise, every column of $A'$ has two $1$'s.




---
# References
