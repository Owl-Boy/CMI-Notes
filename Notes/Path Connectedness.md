202302101302

Type : #Note
Tags : [[Topology]]

---
# Path Connectedness
```ad-note
title: 
Given points $x,y \in X$ we say a _path_ in $X$ is a continuous map $f : [a,b] \to X$ with $f(a) = x, f(b) = y$.
```

```ad-note
title:
$X$ is _path connected_ if between any 2 points $x,y \in X$ there exists a path in $X$ from $x$ to $y$.
```

--- 

```ad-note
title: Theorem
If $X$ is path connected then $X$ is connected but the converse is not true.
```

#### Proof:
If X were disconnected, then let $X = A \sqcup B$, let $a \in A, b \in B$, then there is a path $f : [0,1] \to X$ from a to b. Then $f([0,1]) = (A \cap f([0,1])) \cup (B \cap f([0,1]))$ which means $f([0,1])$ is disconnected, which is a contradiction.

Converse is not true:
S = $\{(x,y) | y = sin 1/x, x>0\}$
Let $\bar S = S \cup \{(0,0)\}$.
$\bar S$ is connected but not path connected. It is connected since $S$ is a cts image of $(0,\infty)$ and $\bar S$ lies between $S$ and $Cl(S)$. 
If it were path connected then there would be a path $f:[0,1] \to \bar S$ from $(1/\pi,0)$ to $(0,0)$. hence it would take all $x$ values between 0 and $1/\pi$. 
Then the sequence $\{t_n\}_{n\in \mathbb{N}}$ s.t. $f(t_n) = \left(\dfrac{1}{2n\pi+\pi/2},1\right)$. There is a convergent subsequence $t_n \to t_0$, and since $f$ is continuous, $f(t_0) = (0,1) \notin \bar S$. Contradiction.

---

```ad-note
title: Theorem
If $A \subseteq \mathbb{R}^n$ is open then $A$ connected $\iff A$ path connected.
```

#### Proof:
**Claim**: If $A \subset \mathbb{R}^n$ is open, then the _path components_ (equivalence classes under the relation $x\sim y \iff$ there is a path from x to y) of $A$ are also open.
_Proof_: Let $x \in P \subset A$, where $P$ is a path component, then $B_r(x)$ is contained in $A$ for some $r$, and hence also in $P$ (since it's path connected). $\square$

Now suppose $A$ were not path connected, then there is some $x$ in $A$ such that the path component of $x$ is not the whole of $A$, call it $U$. Then $A = U \sqcup V$ where $V$ is the union of the other path components. But then $V$ = $\phi$ since $U$ is non empty.
Hence $A$ is path connected

---
# Related Problems

---
# References
[[Connectedness]]