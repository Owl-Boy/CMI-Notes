---
tags:
  - Note
  - Incomplete
---
202311021511

Tags : [[Algorithmic Coding Theory]]

---
# Local Self-correction of Bivariate Multiplicity Codes
**Bivariate Multiplicity Codes of Order 2:**
$c(P)=\langle (P(\bar{a})), \frac{\partial P}{\partial X}(\bar{a}),\frac{\partial P}{\partial Y}(\bar{a})\rangle$, $a\in\mathbb{F}_{q}^{2}$, $c(P)\in(\mathbb{F}_{q}^{3})^{q^{2}}$

To correct just $P(\bar{a})$, we can use the evaluations along a random line. How many lines do we need to use in this case?

Let $Q(T)=P(\bar{a}+\bar{b}T)$.
For every $t\in\mathbb{F}_{q}$, the $\bar{a}+\bar{b}T\in L$ coordinate of $c(P)$ completely determines both the value and first order derivative of $Q(T)$ at point $t$.

$\left( Q(t), \frac{\partial Q}{\partial T}(t) \right)=\left( P(\bar{a}+\bar{b}t),b_{1} \frac{\partial P}{\partial X}(\bar{a}+\bar{b}t)+b_{2} \frac{\partial P}{\partial Y}(\bar{a}+\bar{b}t) \right)$

We got a linear combination of the partial derivatives, we wanted them individually. So we pick $b_{1},b_{2}$ and some $\tilde{b}_{1},\tilde{b}_{2}$ and then solve the linear equations to get them back.

We can achieve rates arbitrarily close to 1, by increasing the number of variables (multivariate), and the order of the derivatives we are sending.


---
# References
[[Multiplicity Codes]]