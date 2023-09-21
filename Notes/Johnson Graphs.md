202308201208

Type : #Note
Tags : [[Algebraic Graph Theory]]

---
# Johnson Graphs
**Johnson Graphs** are an important set of graphs that translate many combinatorial problems about sets into graph theory.

```ad-note
title: definition
Let $v,k,i$ be fixed positive integers with $v\ge k\ge i$. Let $\Omega$ be a fixed set of size $v$. Then the vertices of the graph $J(v, k ,i)$ are the subsets of $\Omega$ of size $k$, where two subsets are adjacent if their intersection has size $i$
```

The function that maps each set to its compliment gives the following theorem
$$
J(v, k ,i)\cong J(v, v-k, v-2k+i)
$$

Which also implies that it is safe to assume $v\ge 2k$.

Johnson Graphs for which $i=0$ are called [[Kneser Graph|Kneser Graphs]].

$J(n, m, j)$ is [[T-Transitiviy of Graphs|Vertex Transitive]]
$J(2m+1, m, 0)$ is [[Arc-Transitivity of a Graph|2-Arc-Transitive]] 

---
# References
