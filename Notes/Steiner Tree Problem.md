---
tags:
  - Note
---
202309211309

Tags : [[Advanced Algorithms]]

---
# Steiner Tree Problem

$G=(V,E)$,
costs $c_{uv}\geq 0$ $\forall(u,v)\in E$,
two types of vertices: required and Steiner

**Goal:** To find a min-cost subset $T \subset E$ st $T$ is a tree that includes all required vertices and any subset of Steiner vertices.

---

- **Lemma:** Any approximation for metric case $\implies$ the same approximation for non metric case

---

## Algorithm
Find an $MST$ on terminal vertices.

## Analysis
Let $T$ be an optimal Steiner tree.
Double all edges of $T$ and find an Euler tour (so that later you can go over an edge at most twice).
Obtain a $TSP$ tour by shortcutting and eliminating Steiner vertices.

$\text{cost}(MST) \le \text{cost}(TSP \text{ tour}) \le 2.OPT$

So we get a $2-$approximation.

---
# Generalised Steiner tree/Steiner forest problem

$G=(V,E)$
costs $c_{e}\ge 0$ $\forall e \in E$
$s_{1},t_{1},s_{2},t_{2},\dots,s_{k},t_{k} \in V$

**Goal:** To find a min cost $F \subset E$ s.t. $F$ has a path between $s_{i},t_{i}$ $\forall i$.

---
## LP
## Primal

We want one constraint for each $S \subset V$ s.t. $\exists i S \cap \{s_{i},t_{i}\}=1$
$\delta(S):$ set of edges with exactly one end point in $S$

Minimise $\sum\limits_{e\in E}c_{e}x_{e}$ s.t.
- $\sum\limits_{e\in\delta(S)}x_{e}\ge 1$ $\forall S\subset V, \exists i S\cap\{s_{i},t_{i}\}=1$
- $x_{e}\ge 0$ $\forall e\in E$


## Dual
Maximise $\sum\limits_{S}y_{S}$ s.t.
- $\sum\limits_{S|e\in\delta(S)}y_{S}\le c_e$ $\forall e\in E$
- $y_{S}\ge 0$ $\forall S$

```ad-warning
title: An algo that doesn't work
1. $F= \phi$
Only maintain non zero valued dual variables.
2. Set $y_S=0$ $\forall S$, $x_{e}=0$ $\forall e \in E$.
3. Increase $y_S$ for some $S$. Let $e$ be the edge for which the dual constraint goes tight.
$F=F\cup\{e\}$.
4. Continue until all $s_{i}-t_{i}$ get connected.

$$
\begin{align*}
\text{cost}(F)&=\sum\limits_{e\in F}c_{e}\\
&= \sum\limits_{e\in F}\sum\limits_{S|e\in\delta(S)}y_{S}\\
&= \sum\limits_{S}|F\cap\delta(S)|y_{S}
\end{align*}
$$

$|F\cap\delta(S)|$ can be as large as $k$ or even $\frac{n}{2}$ so we can't bound it.
```


### New algorithm:

Let $C$ be the set of *connected* components $S$ (s.t. $\exists i$ s.t. $S\cap\{s_{i},t_{i}\}=1$) in $G'=(V,F).$
Increase dual variables *simultaneously* for each $S \in C$.

*Observe:* At each iteration, edges that are added to $F$ connect two distinct
connected components. $F$ is a forest.

**Reverse deletion step:** Examine edges in the reverse order of their inclusion in $F$. If their removal keeps each $s_{i}-t_{i}$ connected, remove them. Get $F'$.

```ad-abstract
title: Lemma
For any $C$ in any iteration, $\sum\limits_{S\in C}|\delta(S)\cap F'| \le 2|C|$.
```

```ad-abstract
title: Theorem
$F'$ is a $2-$approximation i.e. $\sum\limits_{S}|F'\cap\delta(S)|y_{S} \le 2\sum\limits_{S}y_{S} \le 2.\text{primal OPT}$
**Proof** by induction on the number of iterations
$$
\begin{align*}
\text{Increase in LHS at an iteration} &=\epsilon\sum\limits_{S\in C}|F'\cap\delta(S)|\\
&\le 2\epsilon|C|\\
&=2\epsilon.\text{ no of dual vars increased in this iteration}\\
&=\text{increase in }RHS\\
\end{align*}
$$
```


---

# References
[[Linear Programming]]