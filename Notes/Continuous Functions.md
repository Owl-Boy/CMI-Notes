202301181801

Type : #Note
Tags : [[Topology]]

---
# Continuous Functions
```ad-info
title: Idea
The idea is to convert the eqsilon delta definitions for metric spaces to topology, with closeness between points is represented by being in a common open set
```
Let $(X, \mathcal T_X)$ and $(Y, \mathcal T_Y)$ be $2$ Topological Spaces and let $f:X\to Y$ be a Topological Space be a function between them. We say $f$ is continuous if $f^{-1}(V)\in \mathcal T_X$ for every $V\in \mathcal T_Y$.

This is a Global Definition, a Local Definition will be given later
**Examples:**
- If a function from $\mathbb R\to \mathbb R$ is continuous in the _Calculus Sense_, then it is continouous in the _Topological Sense_.
- The projection functions from $\mathbb R^{2}\to \mathbb R$ are continuous
- Any function from a discrete space to a topological space is continouous
- Any function from any topological space to the _trivial_ topology is continuous
- Any _Constant_ function from any topological space to any other topological space is continuous
- If $f:X\to Y$ and $g:Y\to Z$ are continuous then $g\circ f:X\to Z$ is continuous
- The identitiy function from $\mathbb R\to\mathbb R_l$ is not continuous, but the identitiy function from $\mathbb R_{l}\to\mathbb R$ is continuous

__Equivalent statements for continuous functions:__ 
- Pre images of _open_ sets are _open_, i.e $f^{-1}(V)\in \mathcal T_X$ for all $V\in\mathcal T_Y$ 
- Pre images of _basic open_ sets are _open_, i.e $f^{-1}(V)\in \mathcal T_X$ for all $V\in\mathcal B$ 
- Pre images of _sub-basic open_ sets are _open_, i.e $f^{-1}(V)\in \mathcal T_X$ for all $V\in\mathcal S$
- Pre images of _closed_ sets are _closed_.
- $f$ is continuous at each point of the topological space. (Local Definition)
- For every subset $A\subset X$, $f(Cl \ A) \subset Cl \ f(A)$. 

**Continuity at a point**:
```ad-note
title: 
$f: X \to Y$ is continuous at a point $x \in X$ if for every open set $V \in \mathscr{T}_Y$ containing $f(x)$, there exists an open set $U \in \mathscr{T}_X$ containing $x$ such that $f(U) \subset V$.
```

**Local formulation of continuity**:
```ad-note
title:
The map $f : X \to Y$ is continuous iff $X = \bigcup\limits_{\alpha} U_{\alpha}$ for open sets $U_{\alpha}$ such that $f|_{U_{\alpha}}$ is continuous for all $\alpha$.
```
- Apparantly, this is useful in Algebraic geometry. (Grothendieck topology)

**Pasting Lemma**:
```ad-note
title:
Let $X = A \cup B$ where A and B are closed (or open) in X. Let $f : A \to Y$
and $g : B \to Y$ be continuous functions. If $f(x) = g(x)$ for all $x \in A \cap B$, then f and g ‘glue together’ to
give a continuous function $h : X \to Y$ obtained by setting $h(x) = f(x)$ if $x \in A$ and h(x) = g(x) if $x \in B$.
```
- Basically this says that if $X$ is a disjoint union of two clopen sets, then I can define a continuous function on $X$ by defining it independently on A and B.
- The infinite analogue of this for the closed case is not necessarily true, for example: just take the closed sets to be singletons in $\mathbb{R}$, standard topology. Being continuous on these closed sets tells us nothing about the continuity of the function as a whole.
---
# Related Problems

---
# References
[[Homeomorphisms]]