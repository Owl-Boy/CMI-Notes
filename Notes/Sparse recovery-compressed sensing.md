---
tags:
  - Note
  - Incomplete
---
202311161511

Tags : [[Algorithmic Coding Theory]]

---
# Sparse recovery-compressed sensing

```ad-tip
title: Motivation
$x \in\mathbb{C}^{n}$ vector is $L-$*sparse* (# non zero entries $=L$)
The goal is to design a *measurement matrix* $M_{(m\times n)}$ s.t. given $y=Mx$, we can uniquely reconstruct $x$. $m$ should be as small as possible.
```

**Obs:** A measurement matrix $M$ can distinguish between all $L-$sparse vectors iff for every subset $\mathcal{L}$ of upto $2L$ columns the right kernel of the submatrix $M|_{\mathcal{L}}$ is zero.

*L-disjunct matrix:* An $m\times n$ binary matrix is $L-$disjunct if for any choice of $L+1$ columns $M_{0},\dots,M_{L}$, $\bigcup\limits_{i\in[L]}supp(M_{i})\not\subseteq supp(M_{0})$.

**Restricted Isometry Property (RIP):**
$m\times n$ matrix $M$; for every $\mathcal{L}\subseteq[n]$, $|\mathcal{L}|\leq L$ and every column vector $x \in\mathbb{C}^{|\mathcal{L}|}$,
$(1-\alpha) \lvert x \rvert_{p}\leq \lvert M|_{\mathcal{L}}.x \rvert_{p}\leq(1+\alpha)\lvert x \rvert_{p}$.


---
# References
