---
tags:
  - Note
  - Incomplete
---
202311011411

Tags : [[Advanced Algorithms]]

---
# Minimum k-cut Problem
Given $G=(V,E)$ undirected graph with weight function on edges, find min wt set $E'\subset E$ s.t. removal of $E'$ disconnects $G$ into $k$ connected components.

There exists an $\tilde{O}(n^{k^{2}})$ algorithm.
NP hard for non constant $k$. (We call the optimisation version of an NP complete decision problem NP hard.)

Today we will look at a $2\left( 1- \frac{1}{k} \right)$ approximation using *Gomory-Hu trees*.

---

We can store pairwise $s-t$ min-cuts $\forall s,t\in V$, in a $V\times V$ matrix, which takes $O(V^{2})$ space. Gomory-Hu trees can do this in $O(V)$ space.
We can find a global min-cut, and recursively find global min-cuts in the two components.

---
$T$ is a **Gomory-Hu tree** for $G$ if:
- $T=(V,F)$, weights $w'\geq 0$, and
- for every $(u,v)\in F$, $w'(u,v)=w(\text{a }u-v\text{ min-cut in }G)$ and $T \setminus \{ (u,v) \}$ is the $u-v$ mincut in $G$.

```ad-tip
title:
**Theorem:** Let $(s-t)$ be a min wt edge on the path between $u$ and $v$ in $T$.
Then $w'(s,t)=w(\text{a }u-v\text{ min-cut in }G)$.
*Proof:* Induction on the length of $u-v$ path
Length = 1; it follows from definition.

$\text{mincut}_{G}(a,b)\geq \min\{ \text{mincut}_{G}(a,c),\text{mincut}_{G}(b,c) \}$
$w$ is the neighbour of $u$ on a $u-v$ path in $T$.
$$
\begin{align*}
\text{mincut}_{G}(u,v)&\geq \min\{ \text{mincut}_{G}(u,w),\text{mincut}_{G}(w,v) \}\\
&\geq \text{mincut}_{G}(s,t)=w'(s,t)
\end{align*}
$$
```

### Construction:
Maintain a tree on subsets of vertices $S_{1},\dots S_{k}\subset V$, $S_{1}=V$.
At each step, pick an $S_{i}$ s.t. $S_{i}\geq 2$.
Let $u,v\in S_{i}$.
In $G$, contract all the vertices contained in each of the subtrees rooted at $S_{i}$ in $T$. Find a $u-v$ mincut $(W,V'\setminus W)$. Split $S_{i}$ as $S_{i_{1}}=S_{i}\cap W,S_{i_{2}}=S_{i}\cap(V'\setminus W)$.

Prove that this gives a *Gomory-Hu* tree.

---
Back to the algorithm:

1. Find a Gomory-Hu tree $T$ of $G$ and remove its $k-1$ lightest edges. The corresponding cut in $G$ is the required approximation to min-k-cut of $G$.
2. Let $OPT$ partitions be $V_{1}',\dots V_{k}'$. Let $OPT_{i}=$ the set of edges with exactly one endpoint in $V_{i}$.
$\sum\limits_{i=1}^{k}w(OPT_{i})=2w(OPT)$.
$w(OPT_{k})\geq \frac{2}{k}w(OPT)$.
If $w(OPT_{k})$ is the max among $i=1,\dots,k$, then $\sum\limits_{i=1}^{k-1}w(OPT_{i})\leq 2\left( 1- \frac{1}{k} \right)w(OPT)$
3. Shrink each $V_{i}'$ into one node. Get a new tree $T'$. Root $T'$ at $V'_{k}$.
$w(V_{1}',\text{parent}(V_{1}'))\leq w(OPT)$.
$w'(\text{edges in }T')\geq w'(k-1 \text{ lightest edges in }T)=w(\text{our cut})$.


---
# References
[[Min-cut Problem]]
[[Existence of Gomory-Hu trees]]