---
tags:
  - Note
  - Incomplete
---
202411142311

Tags : [[Set Theory]]
# $\mathbb P$-name
---
>[!definition]
>$\tau$ is a $\mathbb P$-name iff $\tau$ is a relation and 
>$$
>\forall \langle \sigma, p \rangle \in \tau [ \sigma \text{ is a } \mathbb P\text{-name} \land p\in \mathbb P]
>$$

This is nice and well defined because one can define a kind of a rank for this. Where at level $0$ we have the empty relation as a valid name. For the next level, one is allowed to use those empty names with points in $\mathbb P$ as relation and one can build further. The definition will be justified by **Transfinite Recursion.** 

Let $\mathbf{V}^\mathbb P$ be the set of all $\mathbb P$-names. If $M$ is a transitive model for $\text{ZFC}$ one can define $M^\mathbb P=V^\mathbb P \cap M$. so

$$
M^\mathbb P = \{  \tau \in M :\!\!|\!\!: (\tau \text{ is a $\mathbb P$ name})^M\}
$$

---
# References
