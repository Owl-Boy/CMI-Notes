---
tags:
  - Note
  - Incomplete
---
202401091401

Tags : [[Expander Graphs and Applications]]
# Expander Mixing Lemma
---
**Lemma:**


*Proof:*
Fact: Let $u=\left( \frac{1}{\sqrt{ n }}, \frac{1}{\sqrt{ n }},\dots, \frac{1}{\sqrt{ n }} \right)^{t}$, (the normalised uniform vector), $\|u\|_{2}=1$.
Any vector $v\perp u$, $\|Av\|_{2}\leq\lambda\|v\|_{2}$.
//stuff
Let $\chi_{S},\chi_{T}$ be the characteristic vectors for $S,T$.
$$
\chi_{S}(i)= 1 \text{ iff } i \in S, 0 \text{ otherwise}
$$

Remember Cauchy-Schwarz
$|\langle x,y \rangle|\leq \|x\|_{2}\|y\|_{2}$

$e(S,T)=d\chi_{S}^{\perp}A\chi_{T}$
Break $\chi_{S}$ and $\chi_{T}$ into components along $u$, and perpendicular to $u$, to get $\chi_{S}=\alpha u+\chi_{S}^{\perp_{u}}$, and so on. where $\alpha=\frac{|S|}{\sqrt{ n }}$. Do math to get that $|e(S,T)- \frac{d|S||T|}{n}|=d|\chi_{S}^{\perp_{u}}A\chi_{T}^{\perp_{u}}|$
Use CS to get the result.




---
# References
