---
tags:
  - Note
  - Incomplete
---
202310201410

Tags : [[Advanced Algorithms]]

# Edmonds-Karp algorithm for max-flow
---

Ford-Fulkerson's algo takes $O((m+n)|f^{*}|)$ (pseudopolynomial time)

Edmonds-Karp
Algo 1: $O((m+n)\log |f^{*}|)$ (Weakly polytime)
Algo 2: $O(m^{2}n)$

$m=|E|,n=|V|,|f^{*}|=$ value of the max flow

## Algorithm 1
---
Same as Ford-Fulkerson except choose a path with maximum capacity in each iteration.

```ad-info
title:**Claim:**
If $f^{*}$ is a max-flow, then $\exists$ an $s-t$ path with capacity $\geq \frac{|f^{*}|}{m}$.
*Proof:* Remove all edges of capacity $< \frac{|f^{*}|}{m}$ from $G$. Either $s-t$ are still connected, or we have a cut of capacity $<|f^{*}|$.
```

$G$ has max flow of size $|f^{*}|$.
After the first iteration, $G_{f_{1}}$ has max flow of size $\left( 1- \frac{1}{m} \right)|f^{*}|$, and so on.
After the $k^{th}$ iteration, $G_{f_{k}}$ has max flow of size $\left( 1-\frac{1}{m} \right)^{k}|f^{*}|$.
We stop when
$$
\begin{align*}
\left( 1-\frac{1}{m} \right)^{k}|f^{*}|&<1\\
|f^{*}|e^{ -k/m }&<1\\
\log |f^{*}|-\frac{k}{m}&<1,\\
\text{and, } k&>m\log |f^{*}|
\end{align*}
$$
We find a max-flow in $m\log |f^{*}|$ iterations.

## Algorithm 2
---
Find an augmenting path by BFS i.e. every iteration, choose a shortest augmenting path.

```ad-info
title: **Lemma:**
Number of iterations $\le mn$.
$d=\text{dist}(s,t)$ at any point.

To prove:
1. $d$ does not decrease.
2. After $\le m$ augmentations, $d$ increases by at least $1$.

The algo finds an augmenting path using only forward edges as long as possible.
After each augmentation, one forward edge gets saturated and disappears from $G$.
After $\le m$ iterations, there is either no $s-t$ path or all $s-t$ paths use a back or cross edge. Thus $d$ increases.
```

This algorithm takes $O((m+n)mn)$ time.

# Generalizations
---
Multiple sources, multiple sinks
Create a super-source and a super-sink, and connect $s$ to all the $s_{i}$, similarly for the sinks.

Upper limit on the amount of flow sent out by $s$
Add a phantom $s_{in}$, connect it to $s_{out}$, and put the limit on the edge.

Upper limits on the amounts of flow through any vertex $v$
Same trick, $v_{in}, v_{out}$ and put limit on the edge.

# Applications
---
1. **Bipartite matchings**
max flow = maximum matchings
2. **Edge-disjoint paths**
To find the number of edge-disjoint paths from $s$ to $t$, put capacity $1$ on each edge and find $s-t$ max-flow.
# Min cost max flow
---
Edges have capacities and costs
Cost of a flow $f = \sum\limits_{(u,v)\in E}s(u,v)f(u,v)$
For $e\in E$ capacity $=c(e)$, cost $=s(e)$

**Goal:** Among all max flows, find one with min cost.

Choose any aug path with minimum cost


---
# References
[[Network Flows]]
