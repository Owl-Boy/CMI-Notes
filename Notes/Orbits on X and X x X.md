202308161104

type : #Example
tags : [[Algebraic Graph Theory]]

#  Orbits on $X$ and $X\times X$
---

The Graph is considered to be transitive here.
### Claim: 
Let $\{O_{1},\dots,O_{r}\}$ be the set of orbits on $\Gamma_{x}$ and $X$ where $O_{1}=\{x\}$ and choose $y_{i}\in O_{i},\forall i\in[2..r]$. Let $\{F_{1},\dots, F_{r}\}$ be the set of  orbits in $X\times X$ and $F_{1}$ is the diagonal
###  Proof
Consider $(x,y_{i})\in F_{i}$ then given any $v\ne u$
we can take $(u, v)$ to $(x, v')$ which can be sent to some $x, y_{i}$ for some $i$ and hence any element is a part of one of $F_{i}$, hence there is a bijection between the set of orbits in $X$ and set of orbits in $X\times X$.

```tikz
\usepackage{tikz-cd}
\begin{document}
\begin{tikzcd}

{(u, v)} \arrow [d, "\alpha"]&\\
{(x, v')} \arrow [r, "\beta"]& {(x, y_i)}
\end{tikzcd}
\end{document}
```

```ad-note
title: Number of orbits.
The above Claim Shows that given any $x$, the number of orbits of $\Gamma_{x}$ on $X$ is the same as the number of orbits on $\Gamma$ on $X\times X$ hence the number of orbits of $\Gamma_{x}$ is the same $x$ for all $x\in X$
```


---
# Related


