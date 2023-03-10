202303011803

Type : #Note
Tags : [[Topology]]

---
# Countably Compact
```ad-note
title:
A space $X$ is called _countably compact_ if every open cover of $X$ has a finite subcover.
```

### Proposition
```ad-note
title:
A first countable space is countably compact iff it is sequentially compact.
```
###### Proof:
If it is sequentially compact, then take a minimal countable cover, take points $x_{1},x_{2},\dots$ such that each $x_{i}$ is in exactly one of the open sets of the cover, then there is a point $x$ such that the element of the cover containing it has infinitely many of these $x_{i}$'s. Contradiction.

If it is countably compact, then take a sequence $x_{1},x_{2},\dots$, assume this is a sequence without any convergent subsequence. Then for any $x_{i}$, there is some $V_{i}$ around it which contains only finitely many of the other $x_{j}'s$. Then let $U = (\bigcup V_{i})^{c}$, so the open cover

---
# Related Problems

---
# References
