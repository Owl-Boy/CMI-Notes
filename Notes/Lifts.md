202304040004

Type : #Note
Tags : [[Topology]]

---
# Lifts
```ad-note
title:
Given $p : E \to B$ a cts map, a _lifting_ of a cts map $f : X \to B$ is a map $\widetilde{f}:X \to E$ such that $p \circ \widetilde{f} = f$.
```

We can always _locally_ lift $f$, that means we can restrict $f$ to a subspace of $Y$ of$X$ so that $f(Y) \subset U \subset X$ where $U$ is evenly covered by $p$, then we can lift $f$ to one of the slices in $E$ above $U$.

### Theorem (Lifting of paths):
```ad-note:
title:
Let $p: E \to B$ be a covering map. Let $f : [0,1] \to B$ be a path with $f(0) = b$. Let $e \in p ^{-1}(b)$, then there is a unique lift $\widetilde{f}:[0,1] \to E$ of the path $f$ such that $\widetilde{f}(0)=e$.
```

##### Proof:
$\exists$ an open covering $\{ U_{\alpha} \}_{\alpha \in J}$ of $B$ such that each $U_{\alpha}$ is evenly covered by $p$.
Preimages $\{ f ^{-1}(U_{\alpha}) \}_{\alpha \in J}$ yield an open covering of $[0,1] \implies$ Lebesgue Number lemma $\implies \ \delta>0$ s.t. for all $x$, we have $(x,x+\delta) \subset f ^{-1}(U_{\alpha}) \implies$ We can find a finite subdivision $0 = \delta_{0} <  \delta_{1} < \dots < \delta_{n} = 1$ such that each $f([s_{i},s_{i+1}])$ lies in one of the $U_{\alpha}$. 
Define $\widetilde{f}(0) = \widetilde{f}(s_{0}):=e$
Assume we have defined $\widetilde{f}(s)$ for $s \in [0,s_{i}]$. Define $\widetilde{f}(s)$ for $s \in [s_{i},s_{i+1}]$ as follows.
We know $f([s_{i},s_{i+1}]) \subset U$ for some U that is evenly covered by $p$.

$p ^{-1}(U) = \bigsqcup_{ i \in I} V_{i}$. Choose $V = V_{i}$ which contains $\widetilde{f}(s_{i})$. Then $p\mid_{V} : V \to U$ is a homeomorphism, it has a continuous inverse $\implies \widetilde{f}(s) := p\mid_{V} ^{-1}(f(s)), \ s \in [s_{i},s_{i+1}]$
$\implies$ repeated finitely many times $\widetilde{f}:[0,1]\to E$
$\implies$ Uniqueness follows since in each step, we only had a unique choice for the extension.

### Theorem(Lifting of homotopies):
```ad-note
title:
Let $p: E\to B$ a covering map. $F : [0,1] \times [0,1]\to B$ be a cts map with $F((0,0))=b$. Let $e \in p ^{-1}(b)$, then there exists a unique lift $\widetilde{F}:[0,1]\times [0,1]\to E$ such that $\widetilde{F}((0,0))=e$.

If $F$ is a path homotopy, then $\widetilde{F}$ is a path homotopy.
```
##### Proof:
Similar idea as before for the first part. (Partition $I \times I$ into squares)

Second part, if $F$ is a path homotopy, then it carries $\{ 0 \}\times [0,1]$ into a single point $b_{0} \in B$.
$\widetilde{F}$ is a lifting $\implies$ this edge is carried by $\widetilde{F}$ to $p ^{-1}(b_{0})$ - Discrete topology.

Since $\{ 0 \}\times[0,1]$ is connected, $\widetilde{F}(\{ 0 \}\times [0,1])$ is a singleton set. Same with $\{ 1 \} \times [0,1]$ implies that $\widetilde{F}$ fixes endpoints for all $t$ as $F$ does.

#### NOTE: Loops don't always lift to loops (See example 1)

### Definition:
```ad-note
title:
Given a covering map $p : E \to B$ and $b_0 \in B$. Let $e_0 \in p^{-1}(b_0)$.
Given a starting point $e_{0}$, there is a uniquely determined endpoint of any lift.

$$
\varphi : \Pi_{1}(B,b_{0}) \to p ^{-1}(b_{0})
$$

$$
\varphi ([f]) = \widetilde{f}(1), \ \widetilde{f}(0) = e_{0}
$$
```
This function is well defined because if $f \simeq_{p} g$ as loops in $(B,b_{0})$ then the homotopy $F$ between them lifts to a homotopy $\widetilde{F}$ between $\widetilde{f}, \widetilde{g}$, and thus, $\widetilde{f}(1) = \widetilde{g}(1)$.

This function $\varphi$ is called the **lifting correspondence** derived from the covering map $p$ (this depends on the choice of $e_{0}$).


### Theorem:
```ad-note
title:
If $E$ is path connected, $\varphi$ is surjective. If $E$ is simply connected, then it is bijective.
```
##### Proof:
If $E$ is path connected, for any $e_{1} \in p ^{-1}(b_{0})$, $\exists$ a path $g$ from $e_{0}$ to $e_{1}$. Then $f := p \circ g$ is a loop in $B$ based at $e_{0}$, and $\varphi([f])=e_{1}$ by definition.

If $E$ is simply connected, take $[f]$ ; $[g]$ s.t. $\varphi([f]) = \varphi([g])$.
$\widetilde{f},\widetilde{g}$ unique liftings beginning at $e_{0}$. Then $\widetilde{f}(1) = \widetilde{g}(1) \implies \widetilde{f}, \widetilde{g}$ are path homotopic with homotopy $\widetilde{F}(s,t)$. Then $F(s,t) = p \circ \widetilde{F}(s,t)$ is a path homotopy between $f,g$. Hence $\varphi$ is injective as well as surjective (simply connected is path connected by definition).

### Theorem (Lifting of any cts function):
```ad-note
title:
Given a connected space $Y$ and a map $f : Y \to X$, let $p : E \to X$ be a covering map. Then if for two lifts $\widetilde{f_{1}}$ and $\widetilde{f_{2}}$ of $f$, $\widetilde{f_{1}}(y_{0}) = \widetilde{f_{2}}(y_{0})$ for some $y_{0} \in Y$, then $\widetilde{f_{1}} = \widetilde{f_{2}}$. (Path and Homotopy lifting is a special case of this.)
```

##### Proof:
Consider the diagram:
```tikz
\usepackage{tikz-cd}
\begin{document}
\begin{tikzcd}
Y
\arrow[rrd,"\tilde{f_2}",bend left]
\arrow[rdd, "\tilde{f_1}", bend right]
\arrow[rd,"! \ g", dashed] 
& & \\
& E \times_X E
\arrow[r,"\pi_2"] 
\arrow[d,"\pi_1"] 
& E 
\arrow[d,"p"]
\\
& E 
\arrow[r,"p"] 
& X
\end{tikzcd}
\end{document}
```

Since $p \circ \widetilde{f_{1}} = p \circ \widetilde{f_{2}}$
$\exists ! \ g$ s.t.  $\pi_{1}\circ g = \widetilde{f_{1}}$ and $\pi_{2}\circ g = \widetilde{f_{2}}$
but $Y$ is connected so $g(Y)$ will be connected, also there exists $y_{0} \in Y$ s.t. $g(y_{0}) = (y_{0},y_{0}) \in \Delta(E)$ and since $\Delta(E)$ is a connected component of $E \times_{X} E$, we get that $g(Y) \subseteq \Delta(E)$ and so, $\pi_{1}\circ g = \pi_{2} \circ g$, and hence $\widetilde{f_{1}} = \widetilde{f_{2}}$.

##### NOTE: Here $\Delta(E) = \{ (e,e)  | e \in E\} \cap E \times_{X} E$. (We can show that this is a clopen subset of $E \times_{X} E$)



---
# Examples
1. Consider $f(s) = (\cos 2\pi s,\sin 2\pi s)$, $s \in [0,1]$, this has many lifts to $\mathbb{R}$ corresponding to each interval $[n,n+1] \subset \mathbb{R}$, if 0 is mapped to $n$ in $\mathbb{R}$.
2. 

---
# References
[[Homotopy of paths]]
[[Lebesgue Number Lemma]]
[[Connectedness]]
[[Path Connectedness]]
[[Simply Connected]]

