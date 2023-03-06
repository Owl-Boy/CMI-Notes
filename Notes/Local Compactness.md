202303021303

Type : #Note
Tags : [[Topology]]

---
# Local Compactness
```ad-note
title:
A space $X$ is called **locally compact** at $x$ if there is a compact subspace $C$ of $X$ such that it contains an open nbhd $V$ of $x$.
$$
x \in V \subset C \subset X
$$

```

### Proposition
```ad-note
title:
Let $X$ be a Hausdorff space. Then $X$ is locally compact iff for every $x \in X$ and every $U$ such that $x \in U \in \tau_{X}$, there is a neighbourhood $V$ of $x$ such that $$
x \in V \subset Cl(V) \subset U \subset X $$
and $Cl(V)$ is compact.
```
##### Proof:
If $X$ is locally compact, then take $x \in X$ and $U$ a nbhd of $x$. Since $X$ is locally compact, we have a compact subset $C$ of $X$ (it is also closed since $X$ is hausdorff) which contains an open nbhd $V$ of $x$. 
Now take $W = V \cap U$ and $K = C-W$, note that $K$ is a closed subset of $C$ and hence is compact, and doesn't contain $x$. Therefore, there is a pair of disjoint open sets $V_{1},V_{2}$ s.t. $x \in V_{1}, K \subset V_{2}$. This gives $Cl(V_{1} \cap W) \subset W \subset U$ and we are done since $Cl(V_{1} \cap W) \subset C$ and hence is compact. 

The other direction is trivial.

### Proposition
```ad-note
title:
Let $X$ be locally compact Hausdorff. If $A \subset X$ is an open or closed subset of $X$, then $A$ is locally compact.
```
##### Proof:
1) If $A$ is closed:
   Since $X$ is locally compact, there is a compact set $C$ and a nbhd $U$ of $x$ such that $x \in U \subset C$. Intersected everything with A.
2) If A is open:
   Use the proposition above.

---
# Related Problems
1. $\mathbb{Q}$ is not locally compact.
2. Any compact space is locally compact.
3. $\mathbb{R}^{n}$ is locally compact.
4. $\mathbb{R}^{\mathbb{N}}$ is not locally compact in the product topology.
5. [[One Point Compactification]]

---
# References
[[Compactness]]
[[Hausdorff Property]]