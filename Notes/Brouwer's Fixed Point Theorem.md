202304041204

Type : #Note
Tags :[[Topology]]

---
# Brouwer's Fixed Point Theorem
```ad-note
title:
If $f : B ^{2} \to B ^{2}$ is continuous where $B ^{2} = \{ (x,y) \in \mathbb{R}^{2} : x ^{2} + y ^{2} \le 1 \}$, then $\exists \ x \in B ^{2}$ s.t. $f(x) = x$.
```
##### Proof 1:
There is no retraction from $B ^{2} \to S ^{1}$ (Retraction: $A \subseteq X$, $r : X \to A$ cts. s.t. $r |_{A} = id_{A}$)
Assume that for some $f : B^{2} \to B^{2}$, $f(x) \neq x$ for all $x \in B^{2}$. Then we can define a retraction $h : B^{2} \to S ^{1}$ as follows:
Take a point $b \in B ^{2}$ and draw that ray origination from the $f(b)$ and passing through $b$, define $h(b)$ to be the point where this ray hits $\partial B^{2}$.
$$
h(x) = x + t(x-f(x)) 
$$
where $t > 0$, such that $|h(t)| = 1$.
We can solve for $t$ using the quadratic formula, so $t$ depends continuously on $x$  and so $h$ is continuous.

This is a retraction from $B^{2}$ to $S ^{1}$, contrary to the fact that there is no retraction between these spaces.
(Refer to [[Retractions]])


##### Proof 2:
###### Lemma:
```ad-note
title:
Let $h : S ^{1} \to X$ cts. Then the following are equivalent.

(1) $h$ is null homotopic.

(2) $h$ extends to a cts map $k: B ^{2} \to X$

(3) $h_{*} : \Pi_{1}(S ^{1}) \to \Pi_{1}(X)$ is the trivial homomorphism.
```
##### Proof:
Refer to [[S^1]].

### Corollary 
```ad-note
title:
$f: S ^{1} \to \mathbb{R}^{2}\setminus \{ (0,0) \}$ is not null homotopic.
```
##### Proof:
Refer to [[S^1]].

### Corollary
```ad-note
title:
$id: S ^{1} \to S ^{1}$ is not null homotopic
```
##### Proof:
Refer to [[S^1]].

##### Proof of Brouwer's fixed point theorem:
Assume $f: B ^{2} \to B ^{2}$ cts s.t. $f$ has no fixed point.
Then define $g : B ^{2} \to \mathbb{R}^{2} \setminus \{ (0,0) \}$, $g(p) = p-f(p)$
For a fixed $p \in S ^{1}$, the points $p, g(p)$ lie in a convex subset of $\mathbb{R}^{2} \setminus \{ (0,0) \}$.
This means there is a straight line homotopy between $g(p)$ and $p$.
$H(p,t) := (1-t)g(p) + tp$
$\implies$ Homotopy of maps : $g|_{S ^{1}} \to \mathbb{R}^{2} \setminus \{ (0,0) \}$
This is $H$ at $t = 0$.
and $i : S ^{1} \to \mathbb{R}^{2}\setminus \{ (0,0) \}$
This is $H$ at $t=1$.

So, $g|_{S ^{1}}$ is not null homotopic by corollary.
But it has an extension to $B ^{2}$ namely $g.$
This is contradictory to our lemma.

---
# References
[[Retractions]]
[[Fundamental Group]]
[[Homotopy of paths]]
