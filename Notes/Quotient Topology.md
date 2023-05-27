202302081802

Type : #Note
Tags : [[Topology]]

---
# Quotient Topology
```ad-info
title: IDEA
An injective function $f :X \to Y$ can be seen as a composition of $g:X \to f(X) = A, i:A\hookrightarrow Y$. Here $g$ is a bijection and $i$ is an injection. 

Now suppose $Y$ were a topo space, what topology can we give to $X$ so that $f$ becomes continuous?
Certainly we can just give it the discrete topology, but that won't give us any info about $Y$. 
So we talk about giving it the _coarsest topology_ that makes $f$ continuous. 
That we can do by giving $A$ the subspace topology of $Y$, and then pulling that topology back to $X$ (this is unique). 

**This idea is about pulling back a topology to make the map continuous.**

Another idea, would be to _PUSH_ a topology onto another space. Suppose $f:X \to Y$ were onto, and $X$ a topo space, what topology can we give to $Y$ to make $f$ continuous? Certainly we can give it the trivial topology  but again we get no info about $X$ then. So we ask what's the _finest_ topology we can give $Y$ to make $f$ [[Continuous Functions|continuous]].
```

## Quotient Topology

```ad-note
title: 
Let $f: X \to Y$ be surjective (here X is a topo space, Y is just a set). 

The _quotient topology_ in Y (induced from X) is the collection of subsets $V \subseteq Y$ s.t. $f^{-1}(V)$ is open in X.
```

## Quotient Map

```ad-note
title:
Let $f:X\to Y$ be a surjective map between topo spaces.
Then $f$ is called a _quotient map_ if $Y$ has the quotient topology from $X$, i.e., $V\subseteq \tau_Y$ iff $f^{-1}(V) \in \tau_X$.

An equivalent characterisation would be to that $V$ is closed in $Y$ iff $f^{-1}(V)$ is closed in $X$.
```

#### A quotient map is a continuous map.
For any subset $C \subseteq X$, C is saturated wrt a surjective function $p : X\to Y$ if $C$ contains every set $p^{-1}(Y)$ that it intersects 
$\therefore$ $C$ = union of fibers of $p$.

#### So, $p$ is a quotient map iff $p$ is continuous and $p$ maps saturated open sets to open sets.

```ad-info
title:
1) Each surjective, cts, open map is a quotient map.
2) Each surjective, cts, closed map is a quotient map.
```

#### Exercise:
Take $\mathbb{R}$ with std topology.
Let $x \sim y \iff x-y \in \mathbb{Z}$.
Then $\mathbb{R}/\sim$ is homeomorphic to $S^1$.

## Theorem
```ad-note
title:
Let $f:X\to Y$ be a quotient map.
Let $B\subset Y$,$A = f^{-1}(B)$ let $g : A \to B$ be the restriction of $f$.
1) If $A$ is open or closed, then $g$ is a quotient map.
2) If $f$ is an open or a closed map, then $g$ is a quotient map.
```
#### Proof:
1) Easy to check that $g$ is cts.
   Suppose $A$ is open, then take a set $V \subset B$, such that $f^{-1}(V)$ is open in $A$. This means that $f^{-1}(V)$ is open in $X$ as well and so, $V$ is open in $Y$ since $f$ is a quotient map. But since $V\subset B$, $V$ is open in $B$. 
   If $A$ were closed, then $f^{-1}(V)$ 
3) Easy to check that $g$ is cts, and open or closed according to whether $f$ is open or closed. Let $U$ be a saturated open set in $A$, then $g(U)$ is open in $B$, and we are done by the previous characterisation of quotient maps.

## Theorem
```ad-note
title: 
Let $f:X \to Y$ be a quotient map. $Z$ be any space. Let $f:X \to Z$ be a function s.t. $h(x) = h(x')$ whenever $f(x) = f(x')$. $g:Y\to Z$ is such that $h = g \circ f$. 

$g$ is cts iff $h$ is. $g$ is a quotient map iff $h$ is.
```
#### Proof:
1) $g$ is cts $\implies$ $g \circ f$ is cts since $f$ is cts
   $h$ is cts $\implies$ $g^{-1}(V) = f(h^{-1}(V))$ is open for open $V \implies g$ is cts.
2) $g$ is quotient map 
   Then $h$ is surjective, since $g$ is.
   Take an $h$-saturated open set in $X$, $h^{-1}(V) = f^{-1}(g^{-1}(V))$. Suppose this is open in $X$. Then $g^{-1}(V)$ is open in $Y$. and then $V$ is open in $Z$. hence $h$ is quotient map.
   
   $h$ is quotient map
   Take g-saturated open set in Y, $g^{-1}(V)$ open in Y, but $g^{-1}(V) = f(h^{-1}(V))$. Therefore, $f^{-1}(g^{-1}(V)) = h^{-1}(V)$ is open in X, and so V is open in Z. Hence g is quotient map.

---
# References
[[Continuous Functions]]
[[Open and Closed Functions]]
