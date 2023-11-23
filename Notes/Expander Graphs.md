---
tags:
  - Note
  - Incomplete
---
202311021611

Tags : [[Algorithmic Coding Theory]]

---
# Expander Graphs
Bipartite graphs: $G=(L,R,E)$

Given any $[n,k]_{2}$ code $C$ with parity check matrix $H$, we'll call the bipartite graph $G_{H}$ with $A_{G_{H}}=H$.
Given a bipartite graph $G=(L,R,E)$, with $|L|\geq |R|$, the corresponding code has parity check matrix $A_{G}$.

$G$ is sparse, each vertex in $L$ has at most a fixed number of neighbours in $R$,...

**Left Regularity:** A bipartitite graph $G=(L,R,E)$ is $D-$left regular if every vertex in $L$ has degree exactly $D$.

**Neighbour Set:**

**Unique Neighbour Set:** For any left vertex set $S\subset L$, a vertex $u\in R$ is called a unique neighbour if it is adjacent to only one neighbour of $S$.

**Bipartite Expander Graphs:** An $(n,m,D,\gamma,\alpha)$ bipartite expander is a $D-$left regular bipartite graph $G=(L,R,E)$, $|L|=n$, $|R|=m$, if for every $S \subset L$ with $|S|\leq\gamma n, |N(S)|\geq\alpha |S|$.

We have existential results, but the natural question is, of course, how to construct expander graphs, which we will take as a black box for the purpose of this course.


Let $G$ be an $(n,n-k,D,\gamma,D(1-\epsilon))$ bipartite expander with $\epsilon < \frac{1}{2}$, then $C(G)$ is an $[n,k,\gamma n]$ binary code.
*Proof:* FTSOC, assume that $C(G)$ has distance at most $\gamma n$.
$\exists$ a non zero codeword $\tilde{c}\in C(G)$, with $wt(\tilde{c})\leq\gamma n$.
Let $S$ be the set of non zero coordinates of $\tilde{c}$.
$r\in U(S)$
$|U(S)|\geq D(1-2\epsilon)|S|>0$, $\epsilon< \frac{1}{2},|S|\geq 1$




---
# References
