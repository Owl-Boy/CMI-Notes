---
tags:
  - Note
  - Incomplete
---
202311151411

Tags : [[Advanced Algorithms]]
# Lovasz Local Lemma
---
$n$ bad events: $A_{1},A_{2},\dots,A_{n}$, each can occur with probability $p_{i}\leq p<1$.
So we know that we can avoid each event individually, we want to show that we can avoid all of them simultaneously.
$Pr[\bigcap\limits_{i=1}^{n}\bar{A}_{i}]>0$
If the events are independent, then $Pr[\bigcap\limits_{i=1}^{n}\bar{A}_{i}]\geq(1-p)^{n}>0$.

**LLL:** If $A_{1},A_{2},\dots,A_{n}$ are events s.t. $Pr[A_{i}]\leq p<1\ \forall i$ and each $A_{i}$ depends on at most $d$ $A_{j}$s, and $ep(d+1)\leq 1$ then $Pr[\bigcap\limits_{i=1}^{n}\bar{A}_{i}]>0$.


## k-SAT
---
$\phi=C_{1}\land C_{2}\land\dots \land C_{m}$
$n$ variables
Let $a=(a_{1},\dots,a_{n})$ be an assignment
$A_{i}:$ Clause $C_{i}$ is not satisfied by $a$

**Lemma:** Any $k-SAT$ formula where each variable appears in at most $\dfrac{2^{k-2}}{k}$ clauses is always satisfiable.
*Proof:* $Pr[A_{i}]=\frac{1}{2^{k}}=p$,
$d=2^{k-2}$ (each clause can share a variable with $\leq \frac{2^{k-2}}{k}k$ clauses)
$4pd=\dfrac{4.2^{k-2}}{2^{k}}=1$
By LLL, $Pr[\bigcap\limits_{i=1}^{n}\bar{A}_{i}]>0$. So there exists an assignment that satisfies all clauses.


## Proof of LLL
---



---
# References
