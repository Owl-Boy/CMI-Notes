202302191902

Type : #Note
Tags : [[Complexity Theory]]

---
# EXP (Complexity Class)
### EXP
```ad-note
title:
Class of decision problems that can be decided by a [[Turing Machines|Determinisitic Turing Machine]] in $O(2^{n^{c}})$ time.
```
$$
EXP = \bigcup_{n\in\mathbb{N}}DTIME\left(2^{n^{c}}\right)  
$$

---
$T:\mathbb{N}\to \mathbb{N}$, any "time bound" function
$DTIME(T(n)):$ any $DTM$ (multitape) can tell whether or not to accept within time $T(n)$

$P=\bigcup\limits_{c\geq 0}DTIME(n^{c})$
$NP=\bigcup\limits_{c\geq 0}NTIME(n^{c})$
$EXP=\bigcup\limits_{c\geq 0}DTIME(2^{n^{c}})$
$NEXP=\bigcup\limits_{c\geq 0}NTIME(2^{n^{c}})$

> [!todo] Look up the $k-$tape to single tape construction, and convince yourself that it's a quadratic time slowdown.

$P\subseteq NP\subseteq EXP\subseteq NEXP$.
We believe all inclusions are strict, but we don't have proofs.

**Theorem:** $P=NP\implies EXP=NEXP$.
*Proof:* Padding argument

**Theorem:** $P\subsetneq EXP$.
*Proof:* The $TM$ $M$ that will accept a language in $EXP$ but not in $P$:
1. Input $w$
2. Run $M_{w}$ on $w$ for $|w|^{\log w}$ steps. If $M_{w}$ accepts then REJECT else ACCEPT.

$L(M)\in DTIME(n^{O(\log n)})\subseteq EXP$
*Claim:* $L(M)\not\in P$.
Suppose $L(M)=L(M_{w_{0}})$ for a polytime bounded ($n^{j}$ for some constant $j$) $TM$ $M_{w_{0}}$.
$L(M)\in DTIME(n^{2})$.
$\exists w$ s.t. $M_{w}=M_{w_{0}}$ and $|w|^{\log w}>|w|^{2j}$.
This contradicts Step 2.


---
# References
[[Complexity Classes]]
[[DTIME(f) Complexity Class]]