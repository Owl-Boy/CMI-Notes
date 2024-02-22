---
tags:
  - Note
  - Incomplete
---
202401101401

Tags : [[Combinatorial Optimisation]]
# Edmond's algorithm for general Matching
---
We describe *Edmond's algorithm* for the [[Matching Problem|Matching problem]] in general, non bipartite graphs.

> [!tip] The idea is to use a matching $M$ to get a larger matching.

We define a *flower* as a *blossom* attached to a *stem* at the vertex in the blossom which has both edges (incident on it in the cycle) unmatched, where a *stem* is an alternating path, and a *blossom* is an odd cycle.
Edmond tries to find an augmenting path, or a find a blossom and shrink it, by constructing an alternating forest rooted at all unmatched vertices.

0. Label all unmatched vertices as even.
1. Take an even vertex $u$. If $u$ has an unlabelled neighbour $v$ then label $v$ as odd, and $M(v)$ as even. ($M(v)$ is the vertex matched to $v$ in $M$.)

> [!note] A vertex gets labelled 'even' (resp. odd) iff it has an even (resp. odd) length alternating path from an unmatched vertex. So vertices that have no **alternating** path from an unmatched vertex will not be labelled by this algorithm.

2. If an even-even edge $(u,v)$ is found then
	1. either $u,v$ belong to the same tree, which implies that a blossom is found! Shrink it to get $G/B, M/B$, continue.
	2. or $u,v$ are in different trees rooted at $v_{1},v_{2}$. Then we have an augmenting path $v_{1}\dots u-v\dots v_{2}$. Augment $M$ and continue.
3. If neither an augmenting path nor a blossom are found in $G/B$, then the current matching $M/B$ in the current graph is maximum. Unshrink the blossoms, extend $M /B$ to $M$ in $G$.

> [!question] Is $M$ maximum in $G$?
> No :( 

4. Repeat.

> [!todo] Exercise: Find a counterexample for the above question.

**Theorem 1:** When the algorithm stops, the matching is maximum in $G$.
**Theorem 2:** $G/B$ has an augmenting path wrt $M/B$ iff $G$ has an augmenting path wrt $M$.

**Observations:**
1. All unlabelled vertices are matched among themselves.
2. All odd vertices are matched, to even vertices.
3. So every matched edge is either $O-E$, or $U-U$. So $|M|=|O|+\frac{|U|}{2}$.

---
## Characterisation of maximum matchings in non-bipartite graphs

**Tutte's theorem:** $G$ has a perfect matching iff $\forall X\subseteq V$, the number of odd sized components in $G\setminus X$ is at most $|X|$.
We see that $|M|\leq \frac{|V|-(o(G\setminus X)-|X|)}{2}$.

**Tutte-Berge formula:**
$$
\max_{M}|M|=\min_{X\subseteq V} \frac{|V|-(o(G\setminus X)-|X|)}{2}.
$$
---
Back to our algorithm
If we take the set $X$ in Tutte-Berge's formula to be the set $O$, i.e. the set of 'odd' vertices, then we get that $G\setminus O$ leaves the vertices in $E$ isolated.
$$
\begin{align}
\frac{1}{2}(|V|-|E|+|O|)&= \frac{1}{2}(2|O|+|U|) \\
&= |M|.
\end{align}
$$
> [!success] This proves that our matching is maximum!

> [!check] This also gives a constructive proof of the Tutte-Berge formula!!

---
## Running time
1. We look at each vertex at most once, and each edge at most once.
2. There can be at most $\frac{n}{2}$ Augment operations. Between two consecutive Augment operations, there can be at most $\frac{n}{2}$ Shrink operations, because a Shrink operation decreases the number of vertices in the graph by at least $2$.
3. The running time of the algorithm is $O(n^{2}m)$. Each traversal takes $O(m)$ time, as any DFS or BFS algorithm, finding an aug path takes $O(mn)$ time.

---
# References
[[Matching Problem]]