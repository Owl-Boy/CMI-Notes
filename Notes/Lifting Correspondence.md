202303281003

Type : #Note
Tags : [[Topology]]

---
# Lifting Correspondence
### Theorem:
```ad-note
title:
Let $p: E\to B$ a covering map. $f : [0,1]\to B$ be a path with $f(0)=b$. Let $e \in p ^{-1}(b)$, then there exists a unique lift $\widetilde{f}:[0,1]\to E$ of the path $f$ such that $\widetilde{f}(0)=e$.
```
##### Proof:
$\exists$ an open covering $\{ U_{\alpha} \}_{\alpha \in J}$ of $B$ such that each $U_{\alpha}$ is evenly covered by $p$.
Preimages $\{ f ^{-1}(U_{\alpha}) \}_{\alpha \in J}$ yield an open covering of $[0,1] \implies$ Lebesgue Number lemma $\implies \ \delta>0$ s.t. for all $x$, we have $(x,x+\delta) \subset f ^{-1}(U_{\alpha}) \implies$ We can find a finite subdivision $0 = \delta_{0} <  \delta_{1} < \dots < \delta_{n} = 1$ such that each $f([s_{i},s_{i+1}])$ lies in one of the $U_{\alpha}$. 
Define $\widetilde{f}(0) = \widetilde{f}(s_{0}):=e$
Assume we have defined $\widetilde{f}(s)$ for $s \in [0,s_{i}]$. Define $\widetilde{f}(s)$ for $s \in [s_{i},s_{i+1}]$ as follows.
We know $f([s_{i},s_{i+1}]) \subset U$ for some U that is evenly covered by $p$.

$p ^{-1}(U) = \bigsqcup_{ i \in I} V_{i}$. Choose $V = V_{i}$ which contains $\widetilde{f}(s_{i})$. Then $p\mid_{V} : V \to U$ is a homeomorphism, it has a continuous inverse $\implies \widetilde{f}(s) := p\mid_{V} ^{-1}(f(s)), \ s \in [s_{i},s_{i+1}]$
$\implies$ repeated finitely many times $\widetilde{f}:[0,1]\to E$
$\implies$ Uniqueness follows.

### Theorem:
```ad-note
title:
Let $p: E\to B$ a covering map. $F : [0,1] \times [0,1]\to B$ be a cts map with $F((0,0))=b$. Let $e \in p ^{-1}(b)$, then there exists a unique lift $\widetilde{F}:[0,1]\times [0,1]\to E$ such that $\widetilde{F}((0,0))=e$.

If $F$ is a path homotopy, then $\widetilde{F}$ is a path homotopy.
```
##### Proof:
Similar idea as before for the first part.
Second part, if $F$ is a path homotopy, then it carries $\{ 0 \}\times [0,1]$ into a single point $b_{0} \in B$.
$\widetilde{F}$ is a lifting $\implies$ this edge is carried by $\widetilde{F}$ to $p ^{-1}(b_{0})$ - Discrete topology.

Since $\{ 0 \}\times[0,1]$ is connected, $\widetilde{F}(\{ 0 \}\times [0,1])$ is a singleton set. Same with $\{ 1 \} \times [0,1]$ implies that $\widetilde{F}$ fixes endpoints for all $t$ is $F$ does.

#### Remark: Loops don't always go to loops
Example: $f:[0,1]\to S ^{1}$ $f(s) = (\cos(2\pi s),\sin 2\pi s)$

#### Given a starting point $e_{0} \in p ^{-1}(b_{0})$, there is a uniquely determined endpoint of any lift.

$$
\varphi : \Pi_{1}(B,b_{0}) \to p ^{-1}(b_{0})
$$

$$
\varphi ([f]) = \widetilde{f}(1), \ \widetilde{f}(0) = e_{0}
$$
### Theorem:
```ad-note
title:
If $E$ is path connected, $\varphi$ is surjective. If $E$ is simply connected, then it is bijective.
```
##### Proof:
If $E$ is path connected, for any $e_{1} \in p ^{-1}(b_{0})$, $\exists$ a path $g$ from $e_{0}$ to $e_{1}$. Then $f := p \circ g$ is a loop in $B$ based at $e_{0}$, and $\varphi([f])=e_{1}$ by definition.

If $E$ is simply connected, take $[f]$ ; $[g]$ s.t. $\varphi([f]) = \varphi([g])$.
$\widetilde{f},\widetilde{g}$ unique liftings beginning at $e_{0}$. Then $\widetilde{f}(1) = \widetilde{g}(1) \implies \widetilde{f} = \widetilde{g}$ are path homotopic with homotopy $\widetilde{F}(s,t)$. Then $F(s,t) = p \circ \widetilde{F}(s,t)$ is a path homotopy between $f,g$.

Since simply connected are path connected by definition, $\varphi$ is surjective.

### Theorem:
```ad-note
title:
$\Pi_{1}(S ^{1}) = \mathbb{Z}$ as a group.
```
##### Proof:
Need to show $\varphi([f]*[g]) = \varphi([f])*\varphi([g])$
$\widetilde{f}(1) = n, \widetilde{g}(1)=m$
$h(s)$

---
# References
