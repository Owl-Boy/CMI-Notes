---
tags:
  - Note
  - Incomplete
---
202311201511

Tags : [[Advanced Algorithms]]
# Inapproximability of Max Independent Set
---
We will assume that MAX-3SAT has no approx $>\frac{7}{8}$ unless P=NP, and reduce it to this problem.

$\phi=(x_{1}\lor \bar{x}_{2}\lor x_{3})\land(x_{2}\lor \bar{x}_{3}\lor x_{4})\land(x_{1}\lor \bar{x}_{2}\lor\bar{x}_{4})$
We make a triangle for each clause, with each variable as a vertex, and then join all the edges (possibly across triangles) that are of the form $(x_{i},\bar{x}_{i})$. Call this graph $G_{\phi}$.
**Claim:** max # satisfiable clauses = size of a max ind set in $G_{\phi}$.
$OPT(\phi)=OPT(G_{\phi})$.
Thus, max ind set cannot be approximated to $> \frac{7}{8}$ unless P=NP.

---
### Theorem
If there is an $\alpha-$approximation for max ind set then there is a $\sqrt{\alpha}-$approximation for the same.

$G=(V,E)$
Define $G^{2}=G\times G,V^{2}=V\times V,E^{2}=\{ ((a,b)(c,d))\ |\ (a,c)\in E or (b,d)\in E \}$.
**Claim:** $(OPT(G))^{2}=OPT(G^{2})$ where $OPT$ is max ind set.

*Proof:* If $S$ is an ind set of size $k$ in $G$ then $S\times S$ is an ind set in $G^{2}$ of size $k^{2}$, If $a,b\in S$ then $(a,b),(b,a),(a,a),(b,b)\in S\times S$ and no two have an edge.

Let $S'$ be an ind set in $G^{2}$.
$S'=\{ (a_{1},b_{1}),(a_{2},b_{2}),\dots,(a_{k},b_{k}) \}$
$S_{1}=\{ a\ |\ \exists b(a,b)\in S' \}$
$S_{2}=\{ b\ |\ \exists a(a,b)\in S' \}$
Both $S_{1},S_{2}$ are ind sets in $G$.
$S'\subseteq S_{1}\times S_{2}$
The larger of $S_{1},S_{2}$, let's say $S_{1}$ has $|S_{1}|\geq \sqrt{ |S'| }$.
$(OPT(G))^{2}=OPT(G^{2})$.

$\alpha-$approx for max ind set in $G$
$\implies \alpha OPT(G^{2})$ size ind set in $G^{2}$
$\implies \sqrt{ \alpha }\sqrt{ OPT(G^{2}) }$ size ind set in $G^{2}$
i.e. $\sqrt{ \alpha  }OPT(G)$ size ind set in $G$.

---
We can get $(1-\epsilon)-$approx i.e. PTAS for ind set:
Apply the reduction $k$ times.
Get $G^{2^{k}}$, apply $\alpha-$approx algo to $G^{2^{k}}$.
Get $\alpha^{1/2^{k}}-$approx for $G$.
We want $\alpha^{1/2^{k}}\geq 1-\epsilon$.
So $k\geq \log \log \frac{1}{\alpha}-\log \log \frac{1}{1-\epsilon}$.

---
# References
[[Probabilistically Checkable Proof]]