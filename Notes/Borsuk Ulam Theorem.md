202304041504

Type : #Note
Tags : [[Topology]]

---
# Borsuk Ulam Theorem
```ad-note
title:
```
```ad-note
title:
$f : S ^{2} \to \mathbb{R}^{2}$ is a continuous map, $\implies$ there is a pair of antipodal points $\pm x \in S ^{2}$ such that $f(x) = f(-x)$.
```
For the case when $S^{2}$ is replaced by $S ^{1}$, we can just take $g(x) = f(x)-f(-x)$. 

### Definition:
```ad-note
title:
$x \in S^n$ then a continuous map $h : S^n \to S^m$ is _antipode preserving_ if $h(-x) = -h(x)$
```
Example: $r_{\theta} : S ^{1} \to S ^{1}, \ \ z \mapsto e ^{i\theta}z$

### Lemma:
```ad-note
title:

(1) Composition of two antipode preserving maps is antipode preserving.

(2) $h : S^1 \to S^1$ is null homotopic, then $r_\theta \circ h$ is also null homotopic for any $\theta$. 
```

### Theorem:
```ad-note
title:
If $h : S^1 \to S^1$ is continuous and antipode preserving, then $h$ is not null homotopic.
```
##### Proof:
Refer to [[S^1]].

### Corollary:
```ad-note
title:
There is no antipode preserving map $g : S^2 \to S^1$
```
Suppose there is such a $g$. $S ^{1}$ is an equator of $S ^{2}$, then $h := g|_{S ^{1}}$ is antipode preserving map from $S ^{1}$ to $S ^{1}$, $h$ is not null homotopic, but has $g|_{\mathrm{upper\ hemisphere}}$ is an extension to $B ^{2}$. That is a contradiction to Lemma 2 in [[S^1]].


### Corollary:
```ad-note
title:
$f: S ^{2}\to \mathbb{R}^{2}$, $\exists \ x$ s.t. $f(x) = f(-x)$.
```
##### Proof:
Assume not then $g(x) := \dfrac{f(x)-f(-x)}{\mid\mid f(x)-f(-x)\mid\mid}$
$g : S ^{2} \to S ^{1}$ s.t. $g$ is antipode preserving. Contradiction.

---
# Applications
1. An open set in $\mathbb{R}^{2}$ cannot be homeomorphic to an open set in $\mathbb{R}^{n}$ for $n \ge 3$.
   ##### Proof:
   Assume they were a homeomorphism $f : U \to V$ with $U$ an open subset of $\mathbb{R}^{n}$, and $V$ an open subset of $\mathbb{R}^{2}$.
   Then there exists an $x$ and an $r > 0$ such that $Cl(B_{r}(x)) \subset U$, which is homeomorphic to $B ^{n} \supseteq B^3 \supset S^2$. So by restriction, we get a cts and injective map from $S^{2} \to \mathbb{R}^{2}$. This contradicts Borsuk Ulam.
   
---
# References
[[S^1]]
[[Fundamental Group]]
[[Homotopy of paths]]
[[Retractions]]
