202308161038

type : #Example
tags : [[Algebraic Graph Theory]]

#  T-Transitiviy of Graphs
---
```ad-note
title: defintion
Let $t>1$ be an integer. Let $(\Gamma, X)$ be a permutation group. $T$ is said to be $t-$transitive on $X$ if $\forall$ ordered $t-$tuples $(x_{1},\dots,x_{n})$ and $(y_{1},\dots,y_{n})$ of distinct elements, $\exists \alpha\in\Gamma$ such that $\alpha(x_{i})=y_{i}$ for all $i$. For $t=1$ we call $\Gamma$ tranistive
```

- $m-$transitive implies $n-$transitive for all $n\le m$
- Let $x\in X$ and $(\Gamma, X)$ be transitive and $t>1$. T$(t-1)-$transitive on $X\setminus \{x\}$ and conversely.

proof of converse:
```tikz
\usepackage{tikz-cd}
\begin{document}
\begin{tikzcd}
{(z_1, z_2,\dots, z_r)} \arrow[rr, "\alpha"] \arrow[dd, "\beta^{-1}\circ\gamma\circ\alpha"', dashed] &  & {(x, z_2',\dots,z_r`)} \arrow[d, "\gamma"]                   \\
                                                                                                     &  & {(x,w_2',\dots,w_r')} \arrow[lld, "\beta^{-1}"', bend right] \\
{(w_1, w_2,\dots, w_r)} \arrow[rr, "\eta"'] \arrow[rru, "\beta=\delta\circ\eta"']                    &  & {(x, w_2'',\dots, w_r'')} \arrow[u, "\delta"']              
\end{tikzcd}
\end{document}
```

```ad-tip
The second property above is useful for finding transitivity of graphs.
```

---
# Related
[[Orbits on X and X * X]]
[[Generously Transitive]]
[[Kneser Graph]]
[[Edge-Transitive, Non Transitive is Bipartite]]