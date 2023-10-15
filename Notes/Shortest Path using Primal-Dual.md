---
tags:
  - Note
---
202309211309

Tags : [[Advanced Algorithms]]

---
# Shortest Path using Primal-Dual

- $G = (V,E)$, directed,
- non negative weight $w_{uv} \forall (u,v) \in E$,
- two vertices $s,t$
**Goal:** Find a min weight $s-t$ path.

---
## LP
### Primal
Variables $x_{uv}, (u,v) \in E$
Minimise $\sum\limits_{(u,v)\in E}x_{uv}w_{uv}$ s.t.:

```ad-warning
title: One thing that doesn't work
- $\sum\limits_{v|(s,v)\in E}x_{sv}=1$
- $\sum\limits_{v|(v,t)\in E}x_{vt}=1$
- $\sum\limits_{v|(u,v)\in E}x_{uv} - \sum\limits_{w|(w,u)\in E}x_{wu} = 0$ $\forall u \in V\setminus\{s,t\}$
- $x_{uv}\geq 0$ $\forall (u,v)\in E$

Because for this LP, two disjoint cycles, one with $s$ and the other with $t$ is a valid solution.
```

$$\sum\limits_{v|(u,v)\in E}x_{uv} - \sum\limits_{w|(w,u)\in E}x_{wu} =
\begin{cases}
	1, & \text{if } u=s \\
	-1, & \text{if } u=t \\
	0, & \text{otherwise.}
\end{cases}$$

$x_{uv}\geq 0$ $\forall (u,v)\in E$.

---
### Dual
Variables $y_v$ $\forall v\in V$
Maximise $y_s-y_t$ s.t.:
$y_u-y_{v}\leq w_{uv}$ $\forall (u,v) \in E$

Do until $t$ is included in $G'$:
1. Start with $y_v=0$ $\forall v\in V$.
	$x_{uv}=0$ $\forall (u,v)\in E$.
2. Increase $y_s$, until one more dual constraint becomes tight.
3. Increase *simultaneously* all the dual variables involved in tight constraints.

- **Primal solution:** $x_{uv}=1$ iff $(u,v) \in$ primal solution
- **Pruning:** In $G'$, keep one $s-t$ path $P$ and discard the remaining edges.

```ad-note
title: Observe
The primal dual algorithm is actually Dijkstra's algorithm.
```

```ad-info
title: Combinatorial interpretation of the dual
**Marble and string analogy-** How far apart can $s$ and $t$ be placed on a number line s.t. $\text{dist}(u,v) \leq w_{uv}$?
```

---
### Optimality

- primal solution = $\sum\limits_{(u,v)\in P}w_{uv}=\sum\limits_{(u,v)\in P}(y_u-y_v)=y_s-y_t$ = dual solution


---
# References
[[Linear Programming]]