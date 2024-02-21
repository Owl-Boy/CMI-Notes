---
tags:
  - Note
  - Incomplete
---
202401241401

Tags : [[Combinatorial Optimisation]]
# Primal-Dual Algorithm for Bipartite Min-cost Perfect Matching
---
paper written stuff

**Given:** $G=(A\cup B,E)$, $w: E\to \mathbb{N}$
**Goal:** Find the min-cost maximum matching.

Make $G$ complete bipartite by adding infinite (large) cost edges, after adding extra vertices to one partition if needed.
**New Goal:** Find the min-cost perfect matching.

### Primal LP
$\min\sum\limits_{a\in A}\sum\limits_{b\in B}c_{ab}x_{ab}$ s.t.
- $\sum\limits_{e\sim a}x_{e}=1\quad\forall a\in A$
- $\sum\limits_{e\sim b}x_{e}=1\quad\forall b\in B$
- $x_{ab}\geq 0\quad\forall a\in A,b\in B$.

### Dual LP
$\max\sum\limits_{a \in A}u_{a}+\sum\limits_{b\in B}v_{b}$ s.t.
- $u_{a}+v_{b}\leq c_{ab}\quad\forall a\in A,b\in B$

$$
\begin{align*}
\text{Value}_{\text{primal}}&=\sum\limits_{a \in A}\sum\limits_{b\in B}c_{ab}x_{ab}\\
&\geq\sum\limits_{a \in A}\sum\limits_{b\in B}(u_{a}+v_{b})x_{ab}\\
&\geq\sum\limits_{a \in A}u_{a}\sum\limits_{b\in B}x_{ab}+\sum\limits_{b \in B}v_{b}\sum\limits_{a\in A}x_{ab}\\
&=\sum\limits_{a\in A}u_{a} +\sum\limits_{b\in B}v_{b}\\
&=\text{Value}_{\text{dual}}.
\end{align*}
$$

To get equality, $\forall a,b\quad x_{ab}=0$ or $c_{ab}=u_{a}+v_{b}$. (Complementary slackness)

## Algorithm
---
1. Start with any feasible solution for dual, say $u_{i}=0\quad \forall i \in A$, $v_{j}=\min\limits_{i}c_{ij}$.
2. Let $F=\{ (i,j)\ |\ v_{i}+v_{j}=c_{ij}\}$. Find a max matching $M \in F$. If $M$ is perfect in $G$, output $M$ and stop.
3. Use $M$ to update the solution:
$\delta=\min\limits_{i\in A\cap L,j\in B\setminus L}c_{ij}-u_{i}-v_{j}>0$
Update dual solution: $u_{i}\leftarrow u_{i}+\delta\quad i\in A\cap L$, $v_{j}\leftarrow v_{j}-\delta\quad j\in B\cap L$.
Update $F$, go back to step 2.

**Obs.:**
1. At each step, one edge $(i,j),i\in A\cap L,j\in B\setminus L$ becomes tight, and gets included in $F$. So $j$ moves from $B\setminus L$ to $B\cap L$.
2. The updated dual solution is feasible.
3. $M\subseteq F$ after updating $F$.

$$
\begin{align}
\text{Update in dual sol value}&=\delta |A\cap L|-\delta |B\cap L| \\
&=\delta(|A\cap L|+|A\setminus L|-|A\setminus L|-|B\cap L|) \\
&=\delta\left( \frac{n}{2}-|C^{*}| \right) \\
&>0.
\end{align}
$$
$C^{*}$ is the min VC over $F$.

---
At each step, at least one vertex moves from $B\setminus L$ to $B\cap L$.
After $O(n)$ iterations, $M$ will get augmented and increase size by $1$.
Thus $O(n^{2})$ iterations, and $O(m)$ for each iteration, which gives $O(mn^{2})=O(n^{4})$ time.

---
# References
[[Linear Programming]]