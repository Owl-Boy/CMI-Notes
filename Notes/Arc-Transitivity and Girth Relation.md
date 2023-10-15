202308251128

type :  #Example  
tags : [[Algebraic Graph Theory]]

#  Arc-Transitivity and Girth Relation
---
**Statement:** Let minimum degree $\delta(G)\ge 3$. Let $G$ be $s$-transitive. Then the girth $g$ satisfies
$$
g\ge 2(s-1)
$$

**Proof:** If $\not\exists$ a cycle then $g=\infty$, nothing to prove. So let $g$ be a positive integer.
If $s\le 2$ then nothing to prove as minimum value for $g$ is $3$
If $s\ge 3$ then we claim that $g\ge s$
Suppose not. Then there exists an arc of length $g$ with its starting and ending vertices the same, and an arc of length $g$ with different starting and ending points. Hence $g\ge s$
![[Drawing 2023-08-25 19.47.12.excalidraw|200]]
Now consider a graph with girth $g$.  And consider the path $g_{0},g_{1},\dots g_{s}$.
Since minimum degree is $3$, consider $z\sim g_{s-1}$. Then the path $g_{0},g_{1}\dots g_{s-1},z$ will also be a path of a cycle because this is an automorphism.

![[Drawing 2023-08-25 19.52.20.excalidraw|200]]

Now we have two cycles that contain $g_{1}$ and $g_{s-1}$, each of which is $g$ long. and the common path is $g-s$ long. If we remove the common part, then we get another cycle, whose length has to be at least $g$ as the graph has girth $g$ hence $2(g-s+1)\ge g$ which proves the theorem.

---
# Related
[[Arc-Transitivity of a Graph]]
[[Arc-Transitivity and diameter]]
