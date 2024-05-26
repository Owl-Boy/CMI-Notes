---
tags:
  - Note
  - Incomplete
---
202403271403

Tags : [[Combinatorial Optimisation]]
# Largest common independent set of a matroid
---
stuff written on paper
.
.
.

**Lemma:** $S\in I$, $|S|=|T|$, $\exists!$ perfect matching $N$ between $S\setminus T$, $T\setminus S$ in $G_{M}(S)$, then $T\in I$.
*Proof:*
We direct the edges in $N$ from left to right, and the rest of the edges in the opposite direction.
$G_{N}$ has no cycle, otherwise we could have alternated along the cycle to get a different perfect matching.
Perform toposort and assume vertices are in ascending order $x_{1}<x_{2}<\dots<x_{t}$.
So $(x_{i},y_{j})$ is not an edge if $j<i$.
Let $T\not\in I$. $\exists$ a circuit $C\subseteq T$.
$C\cap T\setminus S\neq \phi$ because $T \cap S\subseteq S\in I$.

.
.
.

## Algorithm
---
1. $S=\phi$.
2. As long as $\exists e \in E\setminus S$ s.t. $S+e \in I_{1}\cap I_{2}$, $S\leftarrow S+e$.
3. Define $X_{1}^{S}=\{ e \in E\setminus S\mid S+e \in I_{1} \}$, $X_{2}^{S}=\{ e \in E\setminus S\mid S+e \in I_{2} \}$. Construct exchange graph (directed). $D_{M_{1},M_{2}}(S):$ Bipartitions $S$, $E\setminus S$.
$(x,y)$ is an edge if $S-x+y\in I_{1}$.
$(y,x)$ is an edge if $S-x+y\in I_{2}$.
4. Find a shortest $X_{1}^{S}$ to $X_{2}^{S}$ path $P$ in $D_{M_{1},M_{2}}(S)$. $S\leftarrow S \oplus P$.
If no such $P$ exists, declare $S$ as largest set in $I_{1}\cap I_{2}$, stop.

## Correctness
---
**Claim 1:** $S\oplus P \in I_{1}\cap I_{2}$.

**Claim 2:** If a $P$ doesn't exist, then $S$ has largest size in $I_{1}\cap I_{2}$.

**Lemma 1:** Strong base exchange property: $B_{1},B_{2}$ bases of $M$. Then $\forall x \in B_{1}\setminus B_{2}$, $\exists y\in B_{2}\setminus B_{1}$ s.t. $B_{1}-x+y$ and $B_{2}-y+x$ are bases.

**Lemma 2:** Let $S,T \in I$, $|S|=|T|$. Then there is a perfect matching between $S\setminus T$ and $T\setminus S$ in $G_{M}(S)$.

**Lemma 3:** Let $S\in I$, $T$ be such that $|S|=|T|$, and there is a *unique* perfect matching between $S\setminus T$ and $T\setminus S$ in $G_{M}(S)$, then $T \in I$.

*Proof of Claim 2:*
$U:$ set of vertices having a path to $X_{2}^{S}$ in $D_{M_{1},M_{2}}(S)$. $X_{1}^{S}\cap U=\phi$, $X_{2}^{S}\subseteq U$.
To show:
- $r_{1}(U)=|S\cap U|$
- $r_{2}(E\setminus U)=|S\cap E\setminus U|$
$S\cap U\in I_{1}$, and $S\cap U\subseteq$









---
# References
