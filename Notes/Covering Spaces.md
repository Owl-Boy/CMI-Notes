202304032204

Type : #Note
Tags : [[Topology]]

---
# Covering Spaces
```ad-note
title:
Let $p : E \to B$ be a continuous surjective map. We say $p$ _evenly covers_ an open subset $U \subseteq B$ if 
$$
p ^{-1}(U) = \bigsqcup \limits_{ \alpha \in I} V_{\alpha}
$$
where $I$ is some indexing set, $V_{\alpha} \subseteq E$ are disjoint open subsets and for each $\alpha \in I$, $p|_{V_{\alpha}} : V_{\alpha} \to U$ is a homeomorphism.
```
#### NOTE: The sets $V_{\alpha}$ are called **slices**.

```ad-note
title:
Let $p : E \to B$ be a cts surjective map. If every point of $B$ has a nbhd that is evenly covered by $p$, then we say $E$ is a **covering space** of $B$ and $p$ is a **covering map**. B is called the _base_ of the covering.
```

### Proposition:
```ad-note
title:
If $p$ is a covering map, then it is an open map.
```
##### Proof:
Let $U$ be an open set in $E$ and let $e \in U$. Let $p(e) =b$ and let $V$ be an evenly covered nbhd of $b$.
Then $p ^{-1}(V) = \bigsqcup V_{\alpha}$ where one of the $V_{\alpha}$ contains $e$.
Then take $U \cap V_{\alpha}$, this is a nbhd of $e$ such that $p(U \cap V_{\alpha})$ is an open subset of $V$ and hence of $B$, also $b \in p(U  \cap V_{\alpha}) \subseteq p(U)$.
Similarly, for all $x \in U$, there is a nbhd around $p(x)$ in $p(U)$, hence $p(U)$ is open.

### Proposition:
```ad-note
title:
Let $p:E \to B$ a covering map. If $B_0$ is a subspace of $B$, and if $E_0 = p^{-1}(B_0)$, then the map $p_0 := p|_{E_0} : E_0 \to B_0$ is a covering map.
```
##### Proof:
For any point $b \in B_{0}$, there is an evenly covered nbhd $U$. Take $U \cap B_{0}$, $p ^{-1}(U \cap B_{0}) = p ^{-1}(U) \cap p ^{-1}(B_{0}) = \bigsqcup V_{\alpha} \cap p ^{-1}(B_{0})$.
Each $V_{\alpha} \cap p ^{-1}(B_{0})$ is open in $E_{0}$ and is homeomorphic to $U \cap B_{0}$.

### Proposition:
```ad-note
title:
If $p : E \to B$ and $p' : E'\to B'$ are covering maps then $p \times p' : E \times E' \to B \times B'$ is a covering map.
```
##### Proof:
Given $(b,b') \in B \times B'$, there are open nbhds $U,U'$ of $b,b'$ respectively that are evenly covered.
Let $p ^{-1}(U) = \bigsqcup V_{\alpha}$ and $p' ^{-1}(U') = \bigsqcup V'_{\beta}$.
$(p \times p')^{-1}(U \times U') = p ^{-1}(U)\times p' ^{-1}(U') = \bigsqcup V_{\alpha} \times V'_{\beta}$

- See example 2.

- Let $b_{0} = (1,0)$ then $B_{0} := (S ^{1} \times b_{0}) \cup (b_{0} \times S ^{1}) \subset S ^{1} \times S ^{1}$. Then $B_{0}$ is the figure 8 space. Then $E_{0} = p ^{-1}(B_{0})$ is a covering space, $E_{0} = (\mathbb{R} \times \mathbb{Z}) \cup (\mathbb{Z} \times \mathbb{R})$.

---
# Examples
1. $p : \mathbb{R} \to S ^{1}$ given by $p(t) = (\cos(2\pi t),\sin(2\pi t))$ is a covering map.
2. Given the above $p$, we have $p \times p : \mathbb{R}^{2} \to S ^{1} \times S ^{1}$ as a covering map.

---
# References
[[Homeomorphisms]]
[[Continuous Functions]]
