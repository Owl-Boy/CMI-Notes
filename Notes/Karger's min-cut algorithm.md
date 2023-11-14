---
tags:
  - Note
  - Incomplete
---
202310181410

Tags : [[Advanced Algorithms]]

---
# Karger's min-cut algorithm
Problem:

## Randomised Algorithm
Pick an edge uniformly at random and contract it, remove self loops, keep multiple edges. Continue this until two nodes are left. Output the cut between the two nodes.

**Observe:**
- Cut size does not go down in the course of the algorithm
- If min-cut size $=k$, then min degree $\ge k$. So $|E|=m\ge \frac{nk}{2}$.

### Analysis
Let $C$ be a min-cut, $|C|=k$.
$Pr[C\text{ survives first round}]=1-\frac{k}{m}\ge 1-\dfrac{k}{\frac{nk}{2}}=\frac{n-2}{n}$.
Let's say $C$ survives $i^{th}$ round.
$Pr[C\text{ survives } (i+1)\text{st round}]\ge \frac{n-i-2}{n-i}$.
$Pr[C\text{ survives until the end}]\ge \frac{n-2}{n} \frac{n-3}{n-1} \dots \frac{1}{3} = \frac{2}{n(n-1)}$

If $G$ has $q$ min-cuts, $Pr[\text{a mincut survives}]\ge \dfrac{q}{n \choose 2}$.
No. of mincuts in $G\le {n \choose 2}$, so $Pr\le 1$
Time $=O(n^{2})$.

---
### Improving the success prob
Repeat the algo $M$ times.
Find cuts $C_{1},\dots,C_{M}$.
Output $min\{C_{1},\dots,C_{M}\}$.

$Pr[C\text{ is not a mincut}]=Pr[\text{the mincut algo fails }M\text{ times}]\le \left( 1-\frac{1}{n^{2}} \right)^{M}\le e^{ \frac{-M}{n^{2}} }$.
Choose $M=n^{2}\log n$, then failure probability $\le e^{\frac{-M}{n^{2}}}\le e^{-\log n}= \frac{1}{n}$.
Time $=O(n^{4}\log n)$


---
# References
[[Randomised Algorithms]]
