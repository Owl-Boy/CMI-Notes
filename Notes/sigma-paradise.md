---
tags:
  - Note
  - Incomplete
---
202403271203

Tags : [[Games on Graphs]]
# sigma-paradise
---
>[!Definition]
>A subset if $U$ is called a $\sigma$-*paradise* if 
>- $U$ is a $\bar{\sigma}$-trap
>- There exists a Memory-less winning strategy for $\sigma$ on $U$.

>[!attention]
>The definition of a paradise is tailor-made for omega-winning conditions and does not work well with conditions like reachability and co-reachability.

---
>[!Theorem] Lemma
>1. If $U$ is a $\sigma$-paradise, then so is $\text{attr}_{\sigma}(G, U)$.
>2. If $\{ U_{i} \}_{i\in I}$ is a family of $\sigma$-paradises. Then $\bigcup_{i\in I}U_{i}$ is also a $\sigma$-paradise

1. Given $\hat{U}=\text{attr}_{\sigma}(G, U)$ we have an attractor strategy to get to $U$ if we are not already in it. Then we just use the winning strategy for $U$.
2. This point is intuitively obvious but it is not trivial to prove.

---
# References
