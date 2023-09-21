202308281108

Type : #Note
Tags : [[Algebraic Graph Theory]]

---
# Strongly Regular Graphs
```ad-info
title: intuition
The idea of *Strong Regularity*, along with the degree of vertices, also makes the relation between vertices identical, in terms of the number of common vertices
```

Let $G$ be a $k-$regular graphs. Then $G$ is said to be *strongly regular* if $\exists$ constants $a,c$ such that
- $\forall x\sim y$ then the number of $z$ adjacent to both $x$ and $y$ is $a$
- otherwise, the number of adjacent vertices to both vertices is $c$

The Peterson Graph is Strongly regular with $c=1, a=0$.

```ad-info
title: Complement
The Complement of a *Strongly Regular* Graph is also a *Strongly Regular* Graph with $a'=n-2k+c-2$ and $c'=n-2k+a$
```



---
# References
[[Triangular Graphs]]
[[Lattice Graphs]]