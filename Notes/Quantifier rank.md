---
tags:
  - Note
  - Incomplete
---
202311292211

Tags : [[Logic]]
# Quantifier rank
---
*Quantifier rank* is just the number of layers deep quantifiers go in a formula.
- If $\varphi$ is atomic then $\text{qr}(\varphi)=0$
- $\text{qr}(\varphi_1\lor\varphi_2)=\text{qr}(\varphi_1\land\varphi_2)$ which is $\max(\text{qr}(\varphi_1),\text{qr}(\varphi_2))$ 
- $\text{qr}(\varphi)=\text{qr}(\lnot\varphi)$
- $\text{qr}(\exists x \varphi) = \text{qr}(\varphi)+1$

We use the notion $\text{FO[k]}$ to denote the set of first order formulas of rank up to $k$

---
# References
- [[Ehrenfeucht-Fraïssé Game]]
- [[Rank-k Types]]