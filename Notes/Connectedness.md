202302101202

Type : #Note
Tags : [[Topology]]

---
# Connectedness
```ad-note
title:
$X$ is non empty, topological space.
$A$ _separation_ of $X$ is a pair of subsets $U,V$ which are disjoint, open and non empty.
```

```ad-note
title:
$X$ is _connected_ if $\nexists$ a separation of $X$. Otherwise it's called _disconnected_.
```

```ad-note
title:
$X$ is called _totally disconnected_ if only singleton subsets of $X$ are connected.
```

```ad-note
title: Proposition
The following are equivalent:
1) $X$ is disconnected.
2) $\exists$ nonempty, disjoint, closed subsets $A, B$ s.t. $X = A \sqcup B$.
3) $\exists$ a subset $A \subset X$ both open and closed s.t. $A \neq \phi$ or $X$.
4) $\exists$ a non trivial clopen set.
```

```ad-note
title: Lemma
If $T \subset X$ is connected, then $Cl(T)$ is connected too. And if $T \subset T' \subset Cl(T)$ then T' is also connected.
```
#### Proof:
Assume to the contrary that it is not connected.
Then $Cl(T) = T_1 \sqcup T_2$, Then $T = (T_1 \cap T) \sqcup (T_2 \cap T) \implies$ T is disconnected. $T_i \cap T \neq \phi$ because they are open sets of $Cl(T)$ and so intersect T non trivially.

Suppose T' = $T_1 \sqcup T_2$, Then $T' = (C_1 \cap T') \sqcup (C_2 \cap T')$ where $C_1,C_2$ are open subsets of $Cl(T)$. Hence $T = T' \cap T = (T_1 \cap T) \sqcup (T_2 \cap T) = (C_1 \cap T' \cap T) \sqcup (C_2 \cap T' \cap T) = (C_1 \cap T) \sqcup (C_2 \cap T)$ which is a union of open subsets of T. 
Contradiction. 

---

```ad-note
title: Theorem
$\mathbb{R}$ is connected.
```

#### Proof:
Suppose not, then $\mathbb{R} = X \sqcup Y$ where X and Y are open. Let $a \in X, b \in Y$ such that $a < b$. Let $A = X \cap (-\infty,b]$, Let $p = \sup A$. 
If p is in X, then $(p-\epsilon,p+\epsilon) \subset X$ and since $p \neq b$, then this interval is also contained in $(-\infty,b]$ and hence $(p-\epsilon,p+\epsilon) \subset A$, contradiction to sup$ A = p$.
If p is not in $X$, then since $Y$ is open,  $(p-\epsilon,p+\epsilon) \subset Y$, then $p-\epsilon$ is also an upperbound to $A$. Contradiction.


```ad-note
title: Definition
A linearly ordered set $L$ having more than one element is called a _linear continuum_ if
1) $L$ has the least upper bound property
2) If $x < y$, $\exists z$ s.t. $x < z < y$.
```

```ad-note
title: Theorem
If $L$ is a linear continuum then it is connected in the order topology and so are the rays and intervals of $L$.
```

#### proof:
Same as the proof for connectedness of $\mathbb{R}$.

--- 
```ad-note
title: Intermediate Value Theorem
Let $f : X \to \mathbb{R}$ be a continuous map where $X$ is connected. If $a,b\in X$ and $r \in \mathbb{R}$ such that $f(a) < r < f(b)$ then $\exists c \in X$ with $f(c) = r$.
```
#### Proof:
Assume to the contrary that there was no c s.t. $f(c) = r$. Then $X = f^{-1}((-\infty,r) \sqcup f^{-1}((r,\infty))$, contradiction.

```ad-note
title: Theorem
The continuous image of a connected space is connected.
```

```ad-note
title: Theorem
A topological space X is connected iff every [[Continuous Functions|continuous function]] 
$f: X \to \{0,1\}$ is constant.
```

---

# Constructions
1) The union or intersection of connected sets are not connected.
   
2) Union of a collection of connected subspaces of X that all have a point in common is connected.
   #### Proof:
   A cts function f on the union takes a fixed value at the common point, and hence the same value over all of the union. 
   
3) **Finite product** of connected spaces is connected.
   #### Proof:
   Let $f: X\times Y \to \{0,1\}$ then $f((x_1,y_1)) = f((x_1,y_2)) = f((x_2,y_2))$.  You need to show that the restriction of $f$ to X is continuous.
   
4) **Arbitrary product** of connected spaces is connected.
   #### Proof: 
   Let X = $A \sqcup B$, then there is some coordinate where the projection of A and B is disjoint and open and covers that component, and so that component is disconnected. Contradiction.
   **Alternate**: Fix a point $(a_{\alpha}) \in X$. 
   Given any finite subset K of J where $X  = \prod \limits_{\alpha \in J} X_{\alpha}$ let $X_K$ denote the subspace containing all points $x$ such that $x_\alpha = a_\alpha \ \forall \alpha \notin K$. Show that $X_K$ is connected.
   The union Y of all X_K's is connected by construction (2).
   Hence the closure of Y = X is also connected.
   
5) **Quotient** of a connected space is connected.
   #### Proof:
   Quotient map is continuous and surjective, cts maps take connected spaces to connected spaces.
---
```ad-note
title: Proposition
The connected components of a space X are connected disjoint spaces of X, whose union is X, s.t. each non empty connected subspace of X intersects only one of them.
```

---
# Related Problems
[[Local Connectedness]]
[[Path Connectedness]]
[[Local Path Connectedness]]

---
# References
[[Intermediate Value Theorem]]
[[Product topology]]
[[Quotient Topology]]
[[Continuous Functions]]