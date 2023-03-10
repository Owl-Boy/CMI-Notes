202303021603

Type : #Note
Tags :

---
# One Point Compactification

```ad-note
title: Compactification
A compactification of a topological space $X$ is an embedding of $X$ as a dense subspace of a compact topological space.

We only care about compactifications upto homeomorphisms, so we say that two compactifications $f_1 : X \to Y_1$ and $f_2 : X\to Y_2$ are _equivalent_ if there is a homeomorphism $h : Y_1 \to Y_2$ that fixes embedded elements of $X$, i.e., $h(f_1(x)) = f_2(x)$. 
```

### One point compactification 
```ad-note
title:
Let $X$ be a topological space. Let $Y = X \sqcup \{ \infty \}$ where $\infty$ is a formal symbol for an extra point not in $X$. Give $Y$ the topology $\tau_{\infty}$ consisting of: 
1) The open subsets $U \subseteq X$.
2) Complements $Y \backslash C$ of closed and compact subsets $C$ of $X$.
We call $Y$ the one point compactification of $X$.
```
##### Proof of $Y$'s compactness and why $\tau_{\infty}$ is a topology on $Y$:
1) The elements of $\tau_{\infty}$ cover $Y$.
2) Take two elements $V_{1},V_{2} \in \tau_{\infty}$ and a point $x \in V_{1}\cap V_{2}$, 
   If both are subsets of $X$ then their intersection contains a nbhd $W$ containing $x$.
   If neither are subsets of $X$, then their intersection $V_{1}\cap V_{2} = C_{1}^{c} \cap C_{2}^{c} = (C_{1} \cup C_{2})^{c}$ where $C_{1},C_{2}$ are compact and closed subsets of $X$. Hence, their intersection is open.
   If one is a subset and the other is not, then their intersection $V_{1} \cap (Y\backslash C_{2}) = V_{1} \cap (X \backslash C_{2})$ is a intersection of two open sets of $X$ and so is open in $X$ and hence is open in $Y$.
3) Take a cover of $\{ U_{\alpha} \}$ of $Y$, this has a $U_{0}$ which contains $\infty$, but since $Y \backslash U_{0}$ is compact, it has a finite subcover $U_{1},\dots U_{n}$. Hence, $U_{0},U_{1},\dots U_{n}$ is a finite subcover of $Y$.

#### Note:
If $X$ is locally compact and hausdorff, then $Y$ is hausdorff and compact.

### Theorem
```ad-note
title:
Let $X \subseteq Y$ be a subspace of a compact Hausdorff space, such that $Y\backslash X$ consists of a single point. Then $X$ is locally compact and hausdorff.
```
##### Proof:
Since $X$ is a subspace of a hausdorff space then $X$ is hausdorff.
Take a point $x \in X$, then since $Y$ is hausdorff, there exists disjoint open sets $V,U$ such that $x \in V$ and $\infty \in U$, then $U^{c}$ is a compact set containing $x$ and containing $V$ as a neighbourhood around $x$. 

#### The following statement tells us that a One point compactification is unique.
```ad-note
title:
Let $X$ be a locally compact hausdorff space with one point compactification $Y = X \sqcup \{ \infty \}$, and suppose $Y'$ is another compact hausdorff space such that $X \subseteq Y'$ is a subspace with $\mid Y' \backslash X\mid = 1$. Then the unique bijection  $f: Y \to Y'$ that fixes $X$ is a homeomorphism
```

##### Proof:
Since $Y$ is compact and $Y'$ is hausdorff, we only need to show that $f$ is continuous. (refer to [[Homeomorphisms]])
Take an open set $V \subseteq Y'$, now if $V \subseteq X$ then $f^{-1}(V)$ is open in X and we are done.
Otherwise $\infty \in V$, now $f^{-1}(Y'-V)$ is a compact subset of $X$ and so, $f^{-1}(V) = (f^{-1}(Y'-V))^{c}$ is open in $Y$.

```ad-note
title: Corollary
A space $X$ is homemorphic to an open subspace of a compact hausdorff space $X$ is a locally compact hausdorff space.
```

---
# Related Problems

---
# References
