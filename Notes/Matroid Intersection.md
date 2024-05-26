---
tags:
  - Note
  - Incomplete
---
202403201403

Tags : [[Combinatorial Optimisation]]
# Matroid Intersection
---
$Span(S):=\{ e\in E\mid rank(S+e)=rank(S) \}$.
A set $S$ is *closed* if $S=span(S)$.

$E:$ ground set
$M_{1}=(E,I_{1})$, $M_{2}=(E,I_{2})$
$M_{1}\cap M_{2}:=(E,I_{1}\cap I_{2})$, this need not be a matroid.
**Goal:** To find a largest set in $I_{1}\cap I_{2}$.

### Bipartite matching
---
$G=(A\cup B,E)$
$M_{1}=(E,I_{1})$ ... left matching
$I_{1}=\{ F\subseteq E\mid \forall v\in A |F\cap \delta(v)|\leq 1 \}$
$M_{2}=(E,I_{2})$ ... right matching
$I_{2}=\{ F\subseteq E\mid \forall v \in B |F\cap \delta(v)|\leq 1 \}$

### Colourful spanning trees
---
Each edge has a colour from $1,\dots,k$.
**Goal:** To find a spanning tree $T$ of $G$ s.t. $T$ has $\leq 1$ edge of any colour.
$M_{1}=$ Graphic matroid
$I_{1}=\{ F\subseteq E\mid F\text{ is acyclic} \}$
$M_{2}=$ Partition matroid
$I_{2}=\{ F\subseteq E\mid |F\cap E_{1}|\leq 1 \forall 1\leq i\leq k \}$
$I_{1}\cap I_{2}:$ set of colourful forests

### Arborescence
---
Directed graph $D=(V,A)$, $A$ for arcs, $r\in V$.
**Goal:** Find a spanning tree $T$ rooted at $r$, s.t. all edges of $T$ are directed away from $r$. Assume $r$ has no incoming edge in $D$.
$M_{1}=$ graphic matroid
$M_{2}=(A,I_{2})$ partition matroid
$I_{2}=\{ F\subseteq E\mid |F\cap\delta(v)|\leq 1 \}$

## A bound
---
$M_{1}=(E,I_{1})$, $M_{2}=(E,I_{2})$
$S \in I_{1}\cap I_{2}$, $U\subseteq E$
$|S|=|S\cap U|+|S\cap(E\setminus U)|\leq r_{1}(U)+r_{2}(E\setminus U)$.

**Theorem:** For any $S\in I_{1}\cap I_{2}$, any $U\subseteq E$,
$|S|\leq r_{1}(U)+r_{2}(E\setminus U)$.
In particular,
$\max\limits_{S\in I_{1}\cap I_{2}}|S|=\min\limits_{U\in E}(r_{1}(U)+r_{2}(E\setminus U))$.

*Proof:*
*Obs.:* If $U$ satisfies the equality, WLOG $U$ is closed in $M_{1}$. Because if it's not, look at its closure, that would not change $r_{1}$, but it will decrease $r_{2}$, but we already had a minimum.

> [!question] Let $G$ have a colourful spanning tree. $|S|=n-1$. What would a witness $U\subseteq E$ look like?









---
# References
