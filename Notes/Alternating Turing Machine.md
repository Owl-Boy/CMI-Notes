---
tags:
  - Note
  - Incomplete
---
202403081103

Tags : [[Complexity Theory]]
# Alternating Turing Machine
---
2 kinds of non deterministic moves, $Q=q_{acc} \cup Q_{\exists}\cup Q_{\forall}$ :
1. Existential - NP
2. Universal - coNP

It's like a game, and the goal is to reach $q_{acc}$. If we have a strategy to reach it from $C_{start}$, then we accept.

We can now define $ATIME(T(n))$, and $ASPACE(S(n))$.

**Theorem 1:** $ATIME(T(n))\subseteq DSPACE(T(n) \subseteq ATIME(T^{2}(n))$

*Proof.a:* $ATIME(T(n))\subseteq DSPACE(T(n))$:
Let $M$ be an $ATM$ that is $T(n)$ time-bounded.
We want to simulate $M$ in $DSPACE(T(n))$.
Input $x$.
$M$'s run on $x$ is a computation tree of depth $O(T(n))$ with constant degree (at most $|Q|$) internal nodes, labelled $\exists$ or $\forall$.

We do the scam DFS by looking at the sequence $\alpha_{1},\dots,\alpha_{d}$ and evaluate everything at depth $d$, and then move to depth $d-1$, and so on till the sequence becomes shorter and shorter, to evaluate the $C_{start}$. If it evaluates to accept, we accept.

> [!warning] Notice that we never used that $T(n)$ is time constructible, we didn't diagonalise against anything. Because we are given that the $TM$ for takes $T(n)$ time. So we don't have to worry about running out of $T(n)$ space, because we are given that the machine runs only for $T(n)$ time.

*Proof.b:* For the second containment, we do Savitch's theorem thing. Look at the (deterministic) computation graph. We want to know whether there is a path from $C_{start}$ to $C_{final}$, in time $T^{2}(n)$. For each $t$, (we want to check if there is such a path of length $t$) guess a middle vertex $C_{m}$ in the path, and then recursively check if there is a $\frac{t}{2}$ length path from $C_{start}$ to $C_{m}$, and if there is a $\frac{t}{2}$ length path from $C_{m}$ to $C_{final}$.

**Corollary:** $APTIME= \bigcup\limits_{c>0}ATIME(n^{c}) =PSPACE$.

---
**Theorem 2:** $\forall S(n)\geq \log n$, $S(n)$ fully space constructible
$ASPACE(S(n))=DTIME(2^{O(S(n))})$,
which also gives, as a special case $ASPACE(\log n)=P$.

**Corollary:** $APSPACE=EXP$.



---
# References
