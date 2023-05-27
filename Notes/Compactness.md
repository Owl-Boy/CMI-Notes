202302131502

Type : #Note
Tags : [[Topology]]

---
# Compactness
```ad-note
title: Open Cover
$X$ space, let $\mathcal{U}$ be a collection of open subsets of $X$. We say that $\mathcal{U}$ is an open cover of $X$ if $\bigcup\limits_{U \in \mathcal{U}} U = X$ 
```

```ad-note
title: Compact space
$X$ is said to be _compact_ if every open cover of $X$ has a finite subcover.
```
**Example:**
1) $X  = \mathbb{R}$ is not compact.
2) $X = (0,1]$ not compact.
3) $X = \{0\} \cup \{1/n: n \in \mathbb{N}\}$ is compact. (Prove it)

---

```ad-note
title: Lemma
Let $A \subset X$ then $A$ is compact(Lindelof) iff each cover of $A$ by open subsets of $X$ contains a finite(countable) subcover of $A$.
```

```ad-note
title: Proposition
Every closed subspace of a compact space is compact.
```
#### Proof:
Take an open cover of $Y$ (closed subspace of compact space $X$), let it be $\{V = U \cap Y\}$. Then extend this cover to a cover of $X$, $\{U\}\cup X\backslash Y$. Then take a finite subcover and intersect this with $Y$.

```ad-note
title: Proposition
Compact subspace of a Hausdorff space is closed.
```
#### Proof:
Take a point in the complement of the compact subspace $Y$, call it $x_0$. For any point $y \in Y$, we can separate $x_0$ and $y$ using open sets $y \in U_y$ and $x_0 \in V_y$ because $X$ is hausdorff. So we get a family of open sets $\{V_y\}$ around $x_0$, one open set for each $y \in Y$. Take a finite subcover of $\{U_y\}$, and take the corresponding $V_y$'s. Then their intersection is an open set containing $x_0$ but not intersecting $Y$. Hence $X \backslash Y$ is open. $\square$ 

---

```ad-note
title:
Image of a compact set under a cts function is compact.
```

```ad-note
title:Theorem
Let $f: X \to Y$ be a bijective cts map. If $X$ is cpt and $Y$ is hausdorff then $f$ is a homeomorphism.
```
#### Proof:
Let $A$ be closed in $X$, then $A$ is compact, hence $f(A)$ is cpt, and so it's closed by the previous proposition.
Hence $f$ is a closed map, this makes it a homeomorphism. $\square$

---
```ad-note
title:Definition
$f:X \to Y$ is called proper if for all compact subspaces $L$ of Y, $f^{-1}(L)$ is compact.
```

```ad-note
title:Theorem
Let $f :X \to Y$ be a cts map from compact $X$ to hausdorff $Y$. Then
1) f is a proper and closed map.
2) If f is surjective then f is a quotient map.
3) If f is injective then it is an embedding.
4) If f is bijective then it is a homeomorphism.
```

```ad-note
title: Theorem
If 2 spaces $X,Y$ are compact then their product is also compact.
```

#### Proof:
Let $\mathcal{C} = \{W_\alpha\}_{\alpha\in J}$ be a cover of $X \times Y$. For each point $p \in X$, $\{p\} \times Y$ is compact and hence is covered by $\{W_{\alpha_1,p} \cdots W_{\alpha_n,p}\}$.
Let $N_p = W_{\alpha_1,p} \cup \cdots \cup W_{\alpha_n,p}$.
By [[Tube Lemma]], there is a nbhd $U_p$ s.t. $U_p \times Y \subset N_p$.
Therefore, $\{U_p\}_{x \in X}$ is a cover of $X$ hence $\{U_{p_i}\}$ is a cover of $X$. Hence $U_{p_i} \times Y$ covers $X\times Y$, and so $N_{p_i}$ covers $X\times Y$. $\square$

```ad-note
title: Theorem
Arbitrary product of compact spaces is again compact.
This is called [[Tychonoff's Theorem]].
```

```ad-note
title: Proposition
X is compact iff for all collections $\mathcal{C}$ of closed subsets of X having [[Finite Intersection Property]], $\bigcap\limits_{C\in \mathcal{C}} C$ is non empty.
```
#### Proof:
**If X is compact**:
If the intersection of all subsets in $\mathcal{C}$ is empty, then the collection $\{U | U^c \in \mathcal{C}\}$ is an open cover of X, take a finite subcover then $U_1^c, U_2^c \cdots U_n^c$ is a finite subcollection of $\mathcal{C}$ whose intersection is empty, contradicting FIP.

**Converse**:
Take a cover of $X$ which does not have a finite subcover. Now take the complement of each element in this cover, we get a family of closed subsets of $X$ having the FIP. But then the intersection of all elements of the family is non empty and so the cover does not contain some point of $X$ which is a contradiction.

### Theorem
```ad-note
title:
Each closed interval $[a,b]$ in $\mathbb{R}$ is compact.
```

#### Corollary
```ad-note
title:
Any finite product of closed intervals $\displaystyle \prod \limits_{i=1}^{n} [a_{i},b_{i}]$ is compact.
```

### Theorem
```ad-note
title: Heine Borel
A subspace $A$ of $\mathbb{R}^{n}$ is compact iff it is closed and bounded.
```

### Theorem
```ad-note
title:
Let $f : (X,d) \to (Y,d')$ be a continuous map on metric spaces. If $X$ is compact, then $f$ is uniformly continuous.
```


---
# Related Results
1) Compact + Hausdorff $\implies$ Normal


---
# Related Problems
1. $X$ is non empty Hausdorff compact space. If $X$ has no isolated points, i.e. no point $x$ such that $\{ x \}$ is open, then $X$ is uncountable. **(Theorem 27.7 Munkres)**

---
# References
[[Lindelof Space]]
[[Finite Intersection Property]]
[[Tube Lemma]]
[[Homeomorphisms]]
[[Hausdorff Property]]
[[Quotient Topology]]
[[Tychonoff's Theorem]]
