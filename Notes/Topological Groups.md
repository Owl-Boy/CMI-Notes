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
# References
[[Topological Spaces]]
[[Groups]]
[[Continuous Functions]]
