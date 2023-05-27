202303071503

Type : #Note
Tags : [[Topology]]

---
# Normal Spaces
```ad-note
title:
A topological space $X$ is _normal_ if 
1) Every singleton is closed in $X$.
2) for each pair of disjoint closed subsets $A,B \subseteq X$, there is a pair of disjoint open subsets $U,V$ of $X$ such that $A \subset U$ and $B \subseteq V$.
We then say that $U,V$ separate $A$ and $B$.
```

### Lemma:
```ad-note
title:
Let $X$ be $T_{1}$, then $X$ is normal iff for every closed subset $A$ of $X$ and every open subset $U$ containing $A$, there is a open set $V$ containing $A$ and contained in $U$ such that $Cl(V) \subseteq U$. 
```
##### Proof:
Suppose $X$ is normal, then for any $A$ and every open nbhd $U$ of $A$, take $U^{c}$ to be the closed set $B$, then there is a separation of $A$, $U^{c}$ $\implies \exists V,W$ s.t. $A \subseteq V, U^{c} \subseteq W$, this gives $V \subset Cl(V) \subset W^{c} \subset U$. We are done.

Conversely, given $A, B$ disjoint and closed, take $U = B^{c}$ and find $V \subset Cl(V) \subset U$. Then $V$ and $(Cl(V))^{c}$ gives the separation. 

#### NOTE: Subspace and product of normal spaces may not be normal.

### Lemma:
```ad-note
title:
Closed subspace of a normal space is normal.
```

### Lemma:
```ad-note
title:
Let $Y$ be a topo space that is not normal. Then there is a topo space $X$ containing $Y$ as a subspace such that $X$ satisfies the second condition in the definition of a normal space.
```

##### Proof:
Take $X = Y \cup \{\infty\}$, $\tau_{X} = \tau_{Y} \cup \{ X \}$. This is normal since any non empty closed subset of $X$ contains $\infty$, hence they are not disjoint, hence it vacuously satisfies the 2nd condition for a normal space.

### Lemma:
```ad-note
title:
Every regular 2nd countable space is normal.
```

Suppose $X$ is the space with $\mathcal{B}$ as the countable basis. Let $C,D$ be the closed disjoint subsets we wish to separate.

Then for any point $x \in C$, construct a separation $U_{x}, V_{x}$ of $x,D$. Since $\mathcal{B}$ is a basis, there exists some $U \in \mathcal{B}$ such that $x \in U \subseteq U_{x}$. Take the union of such $U's$, since $\mathcal{ B}$ is countable, there is a countable collection of them, let it be $\{ U_{n} \}_{n \in \mathbb{N}}$. Then $U := \bigcup_{n \in \mathbb{N}} U_{n}$ is an open set covering $C$, and not intersecting $D$. Similarly get $\{ V_{n} \}_{n \in \mathbb{N}}$ such that $V := \bigcup_{n \in \mathbb{N}} V_{n}$ is a similar cover for $D$.

The problem is that $U,V$ may intersect. To combat that, consider $U_{n}' := U_n \setminus (\bigcup Cl(V_{n}))$ and $V_{n} ' := V_{n} \setminus (\bigcup Cl(U_{n}))$.

Check that $C \subset U:=\bigcup_{n \in \mathbb{N}} U_{n}', D \subset V := \bigcup_{n \in \mathbb{N}} V_{n}'$ and that $U,V$ are disjoint.




---
# Examples
1. $\mathbb{R}_{\ell}$.
   It is $T_{1}$, for any element $a$ of $A$, choose $[a,x_{a})$ such that it doesn't intersect $B$, similarly do for all elements of $B$. Then $U := \bigcup_{a \in A} [a,x_{a})$ and $V := \bigcup_{b \in B} [b,x_{b})$ forms a separation.
2. $\mathbb{R}_{\ell}^{2}$ is **not** normal.
   - Take the diagonal, $y=-x$ this is a closed discrete subspace of $\mathbb{R}_{\ell}^{2}$. Then the subset $A := \{ (x,-x) | x \in \mathbb{Q} \}$ is closed in the parent space, similarly $B := \{ (x,-x) | x \notin \mathbb{Q} \}$ is also closed in the parent space.
   - Take a separation $U,V$ of $A,B$. 
   - Let $K_{n}$ be the set of irrationals $x \in \mathbb{R}$ such that $\left[ x,x+\frac{1}{n}\right) \times [-x,-x+\frac{1}{n}) \subseteq V$.
   - Then $\mathbb{R}$ is a union countably many one point sets ($\mathbb{Q}$) and $K_{n}'s$.
   - By baire category, $\bar{K}_{n}$ has an interval $(a,b)$.
   - Then the parallelogram $(x,-x+\epsilon)$ for which $a< x<b; 0<\epsilon< \frac{1}{n}$ is contained in $V$.
   - Then any rational point on the diagonal in this interval is a limit point of $V$. Contradiction.
3. $\bar{S}_{\Omega} \times \bar{S}_{\Omega}$ is normal since it is Compact and Hausdorff.
---
# Related Results
1) Metrizable $\implies$ Normal
2) Regular, Lindelof $\implies$ Normal
3) Regular, 2nd countable $\implies$ Normal
4) Compact, Hausdorff $\implies$ Normal
5) Every well ordered set is normal in the order topology

---
# Related Problems

---
# References
[[Metrizable Spaces]]
[[Regular Spaces]]
[[Lindelof Space]]
[[Second Countability]]
[[Compactness]]
[[Hausdorff Property]]
[[Order Topology]]
[[Well Ordering]]
[[S_omega]]
