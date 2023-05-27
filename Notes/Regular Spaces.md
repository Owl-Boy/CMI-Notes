202303071503

Type : #Note
Tags : [[Topology]]

---
# Regular Spaces
```ad-note
title:
A topological space $X$ is _regular_ if 
1) Every singleton is closed in $X$.
2) for each point $x \in X$ and closed subset $A \subseteq X$, there is a pair of disjoint open subsets $U,V$ of $X$ such that $x \in U$ and $A \subseteq V$.
We then say that $U,V$ separate $x$ and $A$.
```

### Lemma:
```ad-note
title:
Let $X$ be $T_{1}$, then $X$ is regular iff for every $x$ and every open nbhd U of $x$, there is a nbhd $V$ of $x$ contained in $U$ such that $Cl(V) \subseteq U$. 
```
##### Proof:
Suppose $X$ is regular, then for any $x$ and every open nbhd $U$ of $x$, take $U^{c}$ to be the closed set, then there is a separation of $x$, $U^{c}$ $\implies \exists V,W$ s.t. $x \in V, U^{c} \subseteq W$, this gives $V \subset Cl(V) \subset W^{c} \subset U$. We are done.

Conversely, given $x, A$ disjoint from $x$ and closed, take $U = A^{c}$ and find $V \subset Cl(V) \subset U$. Then $V$ and $(Cl(V))^{c}$ gives the separation. 


### Lemma:
```ad-note
title:
Any subspace of a regular space is regular. An arbitrary product of regular spaces is regular.
```

### Lemma:
```ad-note
title:
Any space admitting a basis with clopen sets is regular.
```
##### Proof:
Suppose $X$ is a space with all basis sets clopen, then take $x$ and $C$ closed, disjoint from $x$. Then $C^{c}$ is open, so there is a basic clopen set $U$ containing $x$. Then $U, U^{c}$ forms a separation.


---
# Examples
1) $\mathbb{R}_{\ell}$
2) $\mathbb{R}^{n}$


---
# Related Results
1) Regular + 2nd Countable $\implies$ Normal
2) Regular + Lindelof $\implies$ Normal
3) Order Topology is Regular
4) Regular + 2nd Countable $\implies$ Metrizable ([[Urysohn Metrization Theorem]])

---
# Related Problems

---
# References
[[Second Countability]]
[[Normal Spaces]]
[[Order Topology]]
[[Lindelof Space]]
[[Urysohn Metrization Theorem]]