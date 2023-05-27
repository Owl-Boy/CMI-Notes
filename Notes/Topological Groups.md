202303310003

Type : #Note
Tags : [[Topology]]

---
# Topological Groups
```ad-note
title:
A topological group $G$ is a group endowed with a topology $\tau_{G}$ such that multiplication and inversion are cts functions in this topology.
```

- If $G$ is a topo group, and $X$ is a topo space, then a topological group action of $G$ on $X$ is a cts map $(g,x) \mapsto gx : G \times X \to X$.

```ad-note
title:
Let $H$ be a topological group satisfying $T_{1}$ condition, then $H$ is a topological group iff the map $H \times H \to H$ sending $(x,y) \mapsto xy ^{-1}$ is cts.
```
##### Proof: 
If $H$ is a topo group then the given map is a composition of two continuous maps hence cts.

Conversely, given that this is cts, then it is cts in both components, so that function $f((1,y)) = y ^{-1}$ is cts.
Hence $f(x,f((1,y))) = xy$ is continuous.

---
# Properties
### Lemma:
```ad-note
title:
On a topological group, the following maps are homeomorphisms:
- Left multiplication or right multiplication by an element.
- inversion
- conjugation by an element
```

#### NOTE: This statement tells us that to look at open nbhds of $g$, it is the same as looking at open nbhds of $e$. 

### Definition:
```ad-note:
title: Homogenous space
A topo space $X$ where for any pair of points $x,y$ there is a homeomorphism from $X$ to $X$ taking $x$ to $y$ is called a homogenous space.
```

### Lemma:
```ad-note
title:
Let $H$ be a subspace of a topo group $G$. Then if $H$ is a subgroup of $G$, then both $H$ and $Cl(H)$ are topo groups.
```

##### Proof:
Take the function $H \times H \to H$ that takes $(x,y)$ to $xy ^{-1}$. This is continuous since it is the restriction of a cts function on $G \times G$ to a subspace.

Similarly, we need to show that if $f : G\times G \to G$ where $f(x,y) = xy ^{-1}$, then $f(Cl(H) \times Cl(H)) \subseteq Cl(H)$. 
But $f(Cl(H) \times Cl(H)) = f(Cl(H \times H)) \subset Cl(f(H \times H)) \subset Cl(H)$
Since $f$ is continous on $G \times G$.

### Proposition
```ad-note
title:
Given $G$, a topo group, and $H$ a subgroup,
1. $G/H$ is a homogenous space.
2. If $H$ is closed, then $G /H$ is $T_{1}$.
3. Show that the quotient map $p : G \to G /H$ is open.
4. if $H$ is closed, and $H \lhd G$ then $G /H$ is topo group.
```
##### Proof:
1. Take two elements $\alpha H, \beta H \in G /H$. Then there is a homeomorphism $f : G \to G$ which is multiplication by $\beta \alpha^{-1}$. But then $g = p \circ f$ is a quotient map. This maps $x$ to $\beta \alpha^{-1}x H$ but then $g(x) = g(y)$ iff $y ^{-1}x \in H$. So this induces a map $G /H \to G /H$ which takes $xH$ to $\beta\alpha^{-1}xH$, and so $\alpha H$ goes to $\beta H$.
2. We know $H$ is closed and that $G /H$ is homogenous, hence any singleton is closed.
3. Let $U$ be open in $G$, then $p ^{-1}(p(U)) = UH = \bigcup \limits_{ h \in H} U\cdot h$ is open. Hence $p(U)$ is open.
4. $H \lhd G$ gives that $G /H$ is a group, $H$ being closed gives this is $T_{1}$.
```tikz
\usepackage{tikz-cd} 
\begin{document} 
\begin{tikzcd}     
G    \arrow[r,"f"] \arrow[d,"p"]& G \arrow[d,"p"] \\
G/H  \arrow[r,"g"] & G/H
\end{tikzcd}
\end{document}
```
Take the map $g : G /H$ to $G/H$, $g(xH) = axH$. This lifts to a map $f : G \to G$; $f(x) = ax$, with the above diagram commuting.
So take an open set $U$ in $G /H$ and then $g ^{-1}(U) = p(f ^{-1}(p ^{-1}(U)))$ which is open since $p$ is an open map.

Similar argument holds when $g(xH) = x ^{-1}H$.

### Lemma:
```ad-note
title:
1) If $H$ is a normal subgroup of $G$ then so is $Cl(H)$.
2) Every open subgroup of $G$ is closed.
3) If $A$ and $B$ are compact sets in $G$ then so is $AB$.
```
##### Proof:
1) $Hg = gH \subseteq g \cdot Cl(H) \implies Cl(H)\cdot g \subseteq g\cdot Cl(H)$. Similarly the other inclusion holds.
2) Let $H$ be an open subgroup of $G$, then $G \setminus H = \bigcup \limits_{ g \notin H} g \cdot H$ which is a union of open sets and hence open. Thus $H$ is closed.
3) $A \times B$ is compact subset of $G \times G$, the multiplication map is continuous, and $AB$ is the image of $A \times B$ under this map.

### Definition:
```ad-note
title:
Let $G,H$ be topo groups. A map of topo groups $G \to H$ is a continuous map that is also a group homomorphism.
```



---
# Examples:
1. Any group with discrete topology.
2. $(\mathbb{Z},+)$, ($S ^{1}$, $\cdot$ )
3. ($\mathbb{R}$,+)
4. ($\mathbb{R}_{+}$, $\cdot$ )
5. $GL_{n}(\mathbb{C}), GL_{n}(\mathbb{R})$
6. $SL_{n}(\mathbb{R}), SL_{n}(\mathbb{C})$.

---
# References
[[Topological Spaces]]
[[Groups]]
[[Continuous Functions]]
[[Quotient Topology]]

