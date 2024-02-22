---
tags:
  - Note
  - Incomplete
---
202401111401

Tags : [[Expander Graphs and Applications]]
# Error Reduction for RP algorithms
---
This is one of the many applications of Expander Graphs.

Let $\mathcal{A}$ be an $RP$ algorithm that uses $r$ random bits and error probability $\leq \frac{1}{3}$.
Independent $k$ times repetition gives error probability $\leq \frac{1}{3^{k}}2^{-\Omega(k)}$
$\#$ of random bits $=O(kr)$

Instead of generating the $r$ random bits independently each time, we can take a $(2^{r},D,\lambda)$ expander graph on $V=\{ 0,1 \}^{r}$, pick a vertex from it at random using $r$ bits, then pick one of its neighbours using $\log D$ bits each time, for $k-1$ times, thus using a total of $r+O(k)$ random bits. ($D$ is constant.)

---
# References
[[Expander Graphs and Applications]]