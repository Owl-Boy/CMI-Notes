202303301003

Type : #Note
Tags : [[Topology]]

---
# 30-03-23 Lecture

$f : [0,1] \to [0,1]$ cts $\implies$ $f$ has a fixed point.
Just take $g(x) = f(x)- x$ apply IMVT.

### Brouwer's fixed point theorem
```ad-note
title:
If $f : B ^{2} \to B ^{2}$ is continuous where $B ^{2} = \{ (x,y) \in \mathbb{R}^{2} : x ^{2} + y ^{2} \le 1 \}$, then $\exists \ x \in B ^{2}$ s.t. $f(x) = x$.
```
##### Proof 1:
There is no retraction from $B ^{2} \to S ^{1}$ (Retraction: $A \subseteq X$, $r : X \to A$ cts. s.t. $r |_{A} = id_{A}$)

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
(1) $\implies$ (2)
$H : S ^{1} \times I \to X$  - homotopy between $h$ and a constant map. 
Define $\Pi : S ^{1} \times I \to B ^{2}$, $\Pi(x,t) = (1-t)x$
Check that $\Pi$ is a quotient map.
$S ^{1} \times \{ 1 \}$ collapses to the point of origin.
Homeomorphism on $S ^{1} \times [0,1) \to B ^{2} \setminus \{ (0,0) \}$
Let $\sim$ denote the equivalence relation given by $\Pi \implies H$ is constant on the fibers
$\implies \phi : (S ^{1} \times I)/\sim \to X$, i.e, $\exists k:B ^{2} \to X$ s.t. $H = k \circ\Pi$
Since $\Pi$ maps $S ^{1} \times \{ 0 \}$ to $S ^{1} = \partial B ^{2}$.
$k |_{S ^{1}} = H|_{S ^{1} \times \{ 0 \}} = h$.

(2) $\implies$ (3)
If $h = k|_{S ^{1}}$ then $h = k \circ i$ where $i : S ^{1} \hookrightarrow B ^{2}$ is the inclusion map.
$h_{*} = k_{*}\circ i_{*}$, but $\Pi_{1}(B ^{2}) = 1$ then $k_{*}$ trivial $\implies h_{*}$ is trivial.

(3) $\implies$ (1) exercise

### Corollary 
```ad-note
title:
$f: S ^{1} \to \mathbb{R}^{2}\setminus \{ (0,0) \}$ is not null homotopic.
```
##### Proof:
$r(x) = \frac{x}{|x|}$ a retraction of $\mathbb{R}^{2}\setminus \{ (0,0) \}$ to $S ^{1}$.
$r \circ i = id_{S ^{1}} \implies r_{*} \circ i_{*} = id_{\Pi_{1}(S ^{1})}$
$\implies i_{*}$ is non trivial $\implies i$ is not null homotopic.

### Corollary
```ad-note
title:
$id: S ^{1} \to S ^{1}$ is not null homotopic
```
##### Proof:
$id_{*} = id:\mathbb{Z} \to \mathbb{Z}$ is non trivial.

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

### Borsuk Ulam Theorem:
```ad-note
title:
$f : S ^{2} \to \mathbb{R}^{2}$ is a continuous map, $\implies$ there is a pair of antipodal points $\pm x \in S ^{2}$ such that $f(x) = f(-x)$.
```
##### Proof:
For $S ^{1}$, Take $g(x) = f(x)-f(-x)$.

For $S ^{2}$:

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
We show that $h_{*} : \Pi_{1}(S ^{1}) \to \Pi_{1}(S ^{1})$ is a non trivial homomorphism.
Let $b_{0} = (1,0)$ and let $h(b_{0}) = a_{0}$.
If $a_{0} = b_{0}$, continue with original $h$, otherwise choose $r_{\theta}: S ^{1}\to S ^{1}$ s.t. $r_{\theta}(a_{0})=b_{0}$, redefine $h:= r_{\theta} \circ h$.

Consider $g : S ^{1} \to S ^{1}$, $g(z) = z ^{2}$.
$g$ is a closed, continuous surjection, in fact a covering map.

$\implies$ The inverse image of any point $w$ on $S ^{1}$ under $g$ consists of two antipodal points, $z$ and $-z$.
$\implies$ In particular, $h$ is a map that is constant on each of the preimages $g ^{-1}(w)$.

$\implies$ $h$ induces $k : S ^{1}\to S ^{1}$. $k \circ q = q\circ h$
$q(b_{0}) =  h(b_{0}) = b_{0} \implies k(b_{0}) = b_{0}$ as well, $k(-b_{0}) = -b_{0}$.

- To show $k_{*}: \Pi_{1}(S ^{1}) \to \Pi_{1}(S ^{1})$ is non trivial
- q is a covering map. Note that if $\widetilde{f}$ is any path in $S ^{1}$, from $b_{0}$ to $-b_{0}$ then $f := g \circ \widetilde{f}$ is a loop that corresponds to a non trivial element in $\Pi_{1}(S ^{1}, b_{0})$. (end point != beginning point)
- Claim: $k_{*}([f])$ is non trivial
$k_{*}([f]) = [k \circ g\circ \widetilde{f}] = [q \circ h \circ \widetilde{f}]$
$h_{0} \circ \widetilde{f}$ is a path in $S ^{1}$ from $b_{0}$ to $-b_{0}$ so that $[g \circ (h\circ \widetilde{f})]$ is not trivial.

- $k_{*}$ is injective.
  Now $q: S ^{1} \to S ^{1}$ is a degree 2 cover. $q_{*} : \Pi_{1}(S ^{1}) \to \Pi_{1}(S ^{1})$ is multiplication by 2.
  $q_{*} \circ h_{*} = k_{*} \circ q_{*}$ is injective, hence $h_{*}$ is injective as well.

### Corollary:
```ad-note
title:
There is no antipode preserving map $g : S^2 \to S^1$
```
Suppose there is such a $g$. $S ^{1}$ is an equator of $S ^{2}$, then $h := g|_{S ^{1}}$ is antipode preserving map from $S ^{1}$ to $S ^{1}$, $h$ is not null homotopic, but has $g|_{\mathrm{upper\ hemisphere}}$ is an extension to $B ^{2}$.

### Corollary:
```ad-note
title:
$f: S ^{2}\to \mathbb{R}^{2}$, $\exists \ x$ s.t. $f(x) = f(-x)$.
```
##### Proof:
Assume not then $g(x) := \dfrac{f(x)-f(-x)}{\mid\mid f(x)-f(-x)\mid\mid}$
$g : S ^{2} \to S ^{1}$ s.t. $g$ is antipode preserving. Contradiction.

# TUTORIAL
- For any topological group $G$, $\Pi_{1}(G,1)$ is abelian.
- 

---
# References
