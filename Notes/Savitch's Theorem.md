---
tags:
  - Note
  - Incomplete
---
202402091102

Tags : [[Complexity Theory]]
# Savitch's Theorem
---
**Theorem:** $S(n)\geq \log n$ is fully space constructible then $NSPACE(S(n))$ is contained in $DSPACE(S(n)^{2})$.

*Proof:* Let $M$ be an $NSPACE(S(n))$ Turing machine.

*Goal:* To construct a $DTM$ $M'$ s.t. $M'$ is $S(n)^{2}$ space bounded and $L(M)=L(M')$.
*Intuitive idea:* Let $w\in\{ 0,1 \}^{n}$ be a length $n$ input for $M$.
Configurations for $M$ are of the form:
(Instantaneous Description) (head position on input tape, Contents of worktape)
size $=O(\log n+S(n))=O(S(n))$
$I_{0}:$ initial configuration
$I_{f}:$ (wlog unique) accepting configuration

Configuration graph $G=(V,E)$
$V:$ set of all configurations, $|V|\leq c^{S(n)}$
$E:$ $I_{1}\mapsto I_{2}$ then $(I_{1},I_{2})\in E$
$M'$ is going to check if there is a directed path from $I_{0}$ to $I_{f}$ in $G$ in space $O(S(n)^{2})$.

$REACH(I_{1},I_{2},i)$ is true if there is a directed path from $I_{1}$ to $I_{2}$ of length $\leq 2^{i}$.

$REACH(I_{0},I_{f},S(n)\log c)$

$REACH(I_{1},I_{2},i)$
if $i=0$ then if $I_{1}=I_{2}$ or if $I_{1}\mapsto I_{2}$, then true;
for each $I'\in V$, do
if $REACH(I_{1},I',i-1)$ and $REACH(I',I_{2},i-1)$, then true;

> [!note] Remark:
> Basically undirected graph reachability has an $O(\log n)^{2}$ space algorithm.

> [!info] Reingold, 2004:
> For undirected graphs, reachability can be solved in $O(\log n)$ space.

$NL=NSPACE(\log n)$
$L=DSPACE(\log n)$
Savitch $\implies NL\subseteq DSPACE(\log^{2}n)$
$L\subseteq NL\subseteq P$
$NL=coNL$
$NSPACE(S(n))=coNSPACE(S(n))$
$NSPACE(n)=CSL$ (Context Sensitive Language)
$2-SAT$ is $NL-$complete under logspace computable reductions



---
# References
