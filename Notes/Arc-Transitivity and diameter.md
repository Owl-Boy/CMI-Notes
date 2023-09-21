202308281040

type : #Example
tags : [[Algebraic Graph Theory]]

#  Arc-Transitivity and diameter
---
### Theorem:
Let $G$ be an $s-$arc transitive graph with $s\ge 4$ and $g=2s-s$. Then the diameter of a graph is $s-1$ and the graph is bipartite.

###  Answer:
The Girth of the graph is $2s-2$. Hence there is a cycle of length $2s-2$ and the diametrically opposite points have distance $s-1$ between them.

Suppose there exists points with distance more than $s-1$. There there are $x, y$ such that the distance between them is exactly $s$. Then let $\alpha=x_{0},x_{1},\dots,x_{s}$. Then map an arc in a cycle of length $2s-2$ onto the $\alpha$. Then the the other arc in the cycle gives a path of length $s-2$ from $x_{0}$ to $x_{s}$ of length $s-2$ which is a contradiction. Hence the diameter of the graph is $s-1$.

To show that it is _bipartite_ we need to show that $G$ has no cycles of length $2t-1$ where $t$ is at least $s$. Consider the smallest such $t$. Such a cycle will be induced. As if there are chords there. Then the cycle will be divided into two parts where one of them would be a smaller odd cycle.

Since the diameter of the graph is $s-1$ then $t\not\ge s$ otherwise the induced odd cycle would have diameter more than $s-1$.

Consider an odd cycle of size $2s-1$ then consider "diametrically opposite points" $z,y$ of $x$.

Consider the path along the cycle $x\rightsquigarrow y\rightsquigarrow z$ which is a path of length $s$. Map an arc of the same length onto it from a cycle of length $2s-2$. This gives another path of length $s-2$ from $x$ to $z$. We also have a path of length $s-1$ from $x$ to $z$. then combining them gives a cycle of length $s-3$ which is a contradiction.

---
# Related
[[Arc-Transitivity and Girth Relation]]
[[Arc-Transitivity of a Graph]]

