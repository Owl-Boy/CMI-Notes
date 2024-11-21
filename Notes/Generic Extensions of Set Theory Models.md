---
tags:
  - Note
  - Incomplete
---
202411142311

Tags : [[Set Theory]]
# Generic Extensions of Set Theory Models
---
If $M$ is a transitive model of $\text{ZFC},\mathbb P\in M$ and $G \subset \mathbb P$ then,
$$
M[G] = \{ \tau_{G} : \tau \in M^\mathbb P \}
$$
>[!lemma]
>If $N$ is a transitive model of $\text{ZFC}$ with $M \subset N$ and $G \in N$, then $M[G] \subseteq N$

For each $\tau\in M^\mathbb P, \tau\in N$ and $G\in N$, then $M[G]\in N$.

This will show that $M[G]$ will be the smallest extension of $M$, once that is proven.

>[!lemma]
>If $M$ is a transitive model of $\text{ZFC},\mathbb P$ is a p.o. in $M$ and $G$ is a non-empty filter on $\mathbb P$, then
>- $\forall x\in M[\check{x}\in M^\mathbb P\land \text{val}(\check x, G)=x]$
>- $M \subset M[G]$
>
>Where $\check x$ is defined as $\check x = \{ \langle\check y, \mathbb 1\rangle: y\in x \}$

Proof be easy.

If $\mathbb P$ is a partial order, then $\Gamma = \{ \langle \check p, p \rangle : p \in\mathbb P\}$
Then we would have $\Gamma_{G} = G$.

>[!lemma]
>$\Gamma_{G}=G$, hence $G\in M[G]$.

>[!lemma]
>Given a transitive $M$ which a model for $\text{ZFC}$ and a non-empty filter $G$ on it.
>- $\forall \tau\in M^\mathbb P(\text{rank}(\tau_{G})\leq \text{rank}(\tau))$
>- $o(M[G])=o(M)$

Proof can be given my induction for the first point. For the second point we have that $M \subseteq M[G]$ and that given any $\tau_{G}$ by the first point the rank of its corresponding name is at least that, hence for every ordinal, consider its corresponding $\mathbb P$-name, which has a greater rank, and hence the set contains at least the same ordinal.

---
# References
