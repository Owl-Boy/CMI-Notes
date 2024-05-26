---
tags:
  - Example
---

202403271204

tags : [[Games on Graphs]]

#  Lemma about Attractor function
---
>[!Theorem] Lemma
>1. The set $V\setminus \text{attr}_{p}(G, X)$ is a $p$-trap in $G$
>2. If $X$ is a $p$-trap in $G$. then so is $\text{attr}_{p'}(G, X)$
>3. $X$ is a $p$-trap in $G$ iff $\text{attr}_{p}(G,V\setminus X)=V\setminus X$.
>4. If $\text{attr}_{p}(G, X) = V\setminus U$ where $U$ is the greatest $p$-trap contained in $V\setminus X$

## Proof
### 1
![[Winning Strategy for Reachability Games#Adler]]

### 2
The $\hat{X}= \text{Attr}_{p'}(G, X)$ is a superset of $X$.
- If the game starts in $v\in X$, $p'$ uses the trapping strategy
- If the games starts in $v \in \hat{X} \setminus X$ then $p'$ uses the reachability strategy to $X$, then uses the trapping strategy.

### 3
- Left to Right
	- If $X$ is a $p$-trap, then the $\text{Attr}_{p}(G, V \setminus X)$ cannot contain any point outside $V \setminus X$ as that would be in $X$ and $p'$ can trap the game in that set.
- Right to Left
	- If $\text{Attr}_{p}(G, V \setminus X)=V \setminus X$, then for any vertex $v\in X$ and $p$ can force the play to go to $V \setminus X$ then it would contradict the fact that $X$ is a $p$-trap.

### 4
There always exist a largest attractor in any restriction of the game as union of arbitrarily many attractors is an attractor.

Given any set $X$, any trap $p$-trap $W\in V \setminus X$ does not intersect with $\hat{X}=\text{attr}_{p}(G, X)$. And from [[Properties of the Attractor function and Traps#1|Point 1]] we know that $U = V \setminus \hat{X}$ is a $p$-trap. 

Also we know that any point in $\hat{X}$ is not in a $p$-trap what does not intersect with $X$.

Hence $U$ is the largest such attractor.

---
# Related
[[Sub-Games]]