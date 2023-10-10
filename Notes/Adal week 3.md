---
tags:
  - Assignment
---

# Adal week 3

Name: Aditi Muthkhod
Roll Number: BMC202107

## Nearest neighbour algo for TSP

Run the nearest neighbour algorithm. Arrange the edges in non increasing order of their weights. $E = \{l_{1},\dots,l_{n}\}.$

```ad-attention
title:  Abuse of notation
We use $l_{i}$ to denote both the edge and the weight of that edge.
```

**Claim:** $l_{1}\le \frac{OPT}{2}$.
*Proof:* Let $a,b$ be the endpoints of $l_{1}$. $OPT$ contains two paths from $a$ to $b$ (one of which might be $l_{1}$ itself). By metric property each of these paths has total weight at least as much as $l_{1}$. So we get $OPT \ge 2l_{1}$.
It follows that $l_{2}\le \frac{OPT}{2}$.

---

**Lemma:** For any edge $l_{i}$, let $a_{i}$ be the endpoint that was chosen before the other endpoint. For any pair of edges $l_{i},l_{j}$, $wt(a_{i},a_{j})\ge\min\{l_{i},l_{j}\}$.
*Proof:*
1. Case I: In our algorithm, $l_{i}$ is chosen before $l_{j}$. Then $wt(a_{i},a_{j}) \ge l_{i}$.
2. Case I: In our algorithm, $l_{j}$ is chosen before $l_{i}$. Then $wt(a_{i},a_{j}) \ge l_{j}$.

---

**Claim:** $l_{2^{k}+1}+\dots +l_{2^{k+1}}\le \frac{OPT}{2}$, $(0\le k\le \lceil\log n\rceil-1)$.
*Proof:*
Let $S$ be the weight of the tour $\mathcal T$ obtained by shortcutting the optimal solution by eliminating all vertices other than $a_{i},\dots,a_{2^{k+1}}$. Every edge in this tour is of the form $(a_{i},a_{j})$ for some $i,j \le 2^{k+1}$. From the previous Lemma, we know that the weight of this edge is at least $\min\{l_{i},l_{j}\}$.
So, $$OPT \ge S \ge\sum\limits_{(a_{i},a_{j})\in\mathcal T}\min\{l_{i},l_{j}\}.$$
Observe that, on the RHS, each term $l_{i}$, specifically for $2^{k}+1\le i\le 2^{k+1}$, can appear at most twice (because $a_{i}$ has exactly two edges of $\mathcal T$ incident on it).
We get
$$OPT \ge S \ge\sum\limits_{(a_{i},a_{j})\in\mathcal T}\min\{l_{i},l_{j}\}\ge 2(l_{2^{k}+1}+\dots+l_{2^{k+1}}),$$
as required.

---

Thus we get that weight of our solution $= l_{1}+\dots+l_{n}\le \frac{\log n}{2}.OPT$, an $O(\log n)$ approximation!

---