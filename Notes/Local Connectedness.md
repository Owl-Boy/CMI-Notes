202302101302

Type : #Note
Tags : [[Topology]]

---
# Local Connectedness
```ad-note
title: 
$X$ is _locally connected_ at $x \in X$ if $\forall$ nbhds $U$ of $x$, $\exists$ a connected nbhd $V$ s.t. $x \in V \subseteq U$.
```

---
```ad-note
title: Proposition
$X$ is locally connected iff for every open set $U$ of $X$, each connected component of $U$ is open in $X$.
```

#### Proof:
If $X$ is LC, then take an open set $U$, and an element $x$ in $U$, then there is a connected nbhd $V$ of $x$ contained in $U$, and so if $C_x$ denotes the connected component of $x$, $V$ is contained in $C_x$. And so each path connected component of $U$ is open in $X$. 

Conversely, for any nbhd $U$ of $x$, there is a connected component of $U$ that contains $x$, take this to be $V$. $\square$

---
# References
[[Connectedness]]