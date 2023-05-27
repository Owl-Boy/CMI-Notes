202304031504

Type : #Note
Tags : [[Topology]]

---
# Homotopy of paths
```ad-note
title:
Let $X,Y$ be two topological spaces.
Let $f,g:X \to Y$ be two continuous maps between them. Then a _homotopy_ between $f,g$ is a continuous map $F : X \times I \to Y$ such that $F(x,0) = f(x)$ and $F(x,1) = g(x)$.


If such a map exists, we say that $f,g$ are homotopic and we write $g \simeq f$. If $f$ is homotopic to the constant map, we say it is nullhomotopic.
```

###### NOTE: When we talk of homotopy of paths $f,g : [0,1] \to X$ we assume that the homotopy fixes their endpoints, since otherwise all paths are homotopic to the constant path.

```ad-note
title:
Two paths $f,g : [0,1] \to X$ are _path homotopic_ if there exists $F : [0,1] \times [0,1] \to X$ such that $F(s,0) = f(s)$ and $F(s,1) = g(s)$ and $F(0,t) =x_0$ and $F(1,t) = x_1$.

Such an $F$ is called a path homotopy and we write $f \simeq_p g$ for this relation between $f,g$.
```

- In particular, for all time $t \in [0,1]$, $f_{t} : [0,1] \to X$ is a path from $x_{0}$ to $x_{1}$.

### Lemma:
```ad-note
title:
The relations $\simeq$ and $\simeq_p$ are equivalence relations on paths.
```
##### Proof:
The relations are obviously symmetric and reflexive.
For transitivity, we can concatenate homotopies.
Say $f \simeq g$ and $g \simeq h$ and $F,G$ are the respective homotopies.
Then we can just take $$H = \begin{cases}
F(s,2t)  & 0 \le t \le \frac{1}{2}\\
G(s,2t-1) & \frac{1}{2} \le t \le 1
\end{cases}$$
giving us a homotopy from $f$ to $h$.

###### NOTE: We denote the homotopy equivalence class of $f$ by $[f]$.

---
# Examples:
1. If $f,g$ are paths in $\mathbb{R}^{2}$, we can define the _straight line_ homotopy between $f,g$ by $$
F(s,t) = (1-t)f(s) + tg(s)
$$
2. In $X = \mathbb{R}^{2} \setminus \set{(0,0)}$, let $f,g$ be paths from $(-1,0)$ to $(1,0)$ such that $f$ stays in the upper half plane and $g$ stays in the lower half plane. Then there is no homotopy between them. 

--- 
# References
[[Continuous Functions]]
