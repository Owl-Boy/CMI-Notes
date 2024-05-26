---
tags:
  - Note
  - Incomplete
---
202403151203

Tags : [[Complexity Theory]]
# Can there be sparse sets that are NP-hard?
---
$A$ is $NP-$hard means $SAT\leq_{m}^{P}A$.

$L\subseteq\Sigma^{*}$ is said to be *sparse* (polynomially sparse) if $\exists$ a polynomial $p$ such that $|L^{\leq n}|\leq p(n)\quad \forall n$.

**Theorem:** If there are sparse $NP-$hard sets then $P=NP$.
$SAT\leq_{m}^{P}$ for some sparse set $S$. $f$ is a polytime reduction.
$\forall F$, $f(F)\in S$ iff $F\in SAT$.

**Obs.:** If there is an $NP-$hard sparse set then there must be an $NP-$complete sparse set.

*Proof:* $|S^{\leq n}|\leq p(n)\implies |f(SAT)^{\leq n}|\leq p(n)$.
So $f(SAT)$ is also sparse.

Given $x \in\Sigma^{*}$ is $x \in f(SAT)$?
> [!hint] Guess $F\in f^{-1}(x)$.
> > [!bug] But $|F|\gg |x|$. $|F|$ may not be poly bounded in $|x|$.
> 
> So we use padding!

$S'=S 10^{*}$. $S'$ is also sparse ✅.
$f':\text{Formulas}\to\Sigma^{*}$
$f'(F)=f(F)10^{|F|}$.
Then we can guess the preimage, and check.
algorithm
.
.
.

**Lemma:** Suppose $\overline{SAT}$ is reducible to a sparse set then $P=NP$.
*Proof:* Given $f$ a reduction from $\overline{SAT}$ to $S$ and $p(n)$ s.t. $|S^{\leq n}|\leq p(n)$ we'll give a polytime algo for $SAT$.
$|f(\text{Formulas of size}\leq m)|\leq q(m)$
$|S^{\leq q(m)}|\leq p(q(m))=r(m)$

We will do a DFS on the tree of all possible assignments to $F(u_{1},u_{2},\dots,u_{n})$.
Here $|F|=m$, and $|F(a_{1},\dots,a_{i},u_{i+1},\dots,u_{n})|\leq m$.
Let $S_{i}:=\phi$, $S$
Until you find a satisfying assignment, do:
Explore a path completely to the end, say $F(0,\dots,0)$, and if it is not satisfiable, put $f(F(0,\dots,0))$ in $S_{i}$, and backtrack.
Every time we explore a new node and backtrack from it, we discover a new thing in the sparse set, and add it (because otherwise we wouldn't have explored that node).










---
# References
