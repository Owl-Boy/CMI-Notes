202308141108

Type : #Note
Tags : [[Algebraic Graph Theory]]

---
# Support of an Automorphism on a Graph
```ad-note
title:definition
The *Support* of an automorphism is the set of objects that are not fixed by the automorphism.
```

### Lemma
Let $m$ be an even number and $|A|=m$ and $A\subset [n]$.
Then $\sigma'$ has the largest number of orbits on $E[n]$ iff $\sigma'$ is an involution that consists of a product of $\frac{m}{2}$ transposition

### Lemma
Let $\sigma\in S_{n}$ such that $\sigma$ is a product of $r$ transpositions and $n-2r$ fixed points. Then $\text{orb}(\sigma')={n\choose 2}-r(n-r-1)$

For the proof, consider the possible transposition of edges.
There are two possible situations
$$
\begin{align*}
\sigma': \{x, y\}\longmapsto \{z, w\}\\
\sigma': \{x, y\}\longmapsto \{x, w\}
\end{align*}
$$
where $x,y,z,w$ are all distinct
For case $2$, there are $(n-2r)\times r$ ways
For case $1$, there are $\frac{1}{2}{r\choose 2}\times 4=r(r-1)$
Hence the total number of transposition are $r(n-r-1)$

---
# References
