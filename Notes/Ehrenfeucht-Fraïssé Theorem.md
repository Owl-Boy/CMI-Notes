---
tags:
  - Note
  - Incomplete
---
202311300011

Tags : [[Logic]]
# Ehrenfeucht-Fraïssé Theorem
---
## Back and Forth Equivalence
This is an additional equivalence that we use to make the proof easier.
- $\mathfrak A\simeq_{0}\mathfrak B$ iff $\mathfrak A \equiv_0\mathfrak B$
- $\mathfrak A\simeq_{k+1}\mathfrak B$ iff
	- **Back:** For every $b$ in $B$, there exists an $a$ such that $(\mathfrak A,a)\simeq_k(\mathfrak B,b)$ 
	- **Forth:** For every $a$ in $A$, there exists a $b$ such that $(\mathfrak A,a)\simeq_k(\mathfrak B,b)$

## Theorem

Then we have that the following are equivalent:
- $\mathfrak A$ and $\mathfrak B$ agree on $\text{FO}[k]$
- $\mathfrak A\equiv_k \mathfrak B$
- $\mathfrak A\simeq_k\mathfrak B$

## Proof
Proof is by induction
**Base Case:** $k=0$ is trivial

**Induction Step:**
To prove the equivalence between points $2$ and $3$. 

for left to right, if  *spoiler* picks $a$ from $A$ and *duplicator* picks $b$ from $B$ in the last round, then we use those choices to define the **Forth** relation.
If the the *spoiler* picks $b$ from $B$, we define the choices for the **Back:** relation.

For the reverse direction, back and forth relation directly gives a strategy for the *duplicator*

To prove the equivalence between $1$ and $3$.

For right to left, pick $a$ from $A$ and let $\alpha_i$ define its rank-$k$ $1$ type. Then $\mathfrak A\models\exists x\alpha_i(x)$. This is a formula of quantifier rank $k+1$. so $\mathfrak B$ also satisfies the formula, which shows the existence of a witnessing $b$. Which means $\text{tp}(\mathfrak A,a)=\text{tp}(\mathfrak B, b)$. So $(\mathfrak A, a)$ and $(\mathfrak B,b)$ agree on the same $\text{FO}[k]$ sentences. And from the hypotheses we have $(\mathfrak A,a)\simeq_k(\mathfrak B,b)$.

For Left to Right
Each formula of rank $k+1$ is a boolean formula that contains rank-$k$ formulas and formulas of form $\exists x\varphi(x)$ where $\varphi$ is rank-$k$. So we can only deal with formulas of the type $\exists x\varphi(x)$
If $\mathfrak A\models\exists x\varphi(x)$, and let $a$ be the witnessing element. Then we have 
$(\mathfrak A,a)\simeq (\mathfrak B, b)$.
By hypothesis we have that these agree on sentences from $\text{FO}[k]$
So we have $\mathfrak B, b\models \varphi(b)$ and hence $\mathfrak B\models\exists x\varphi (x)$. 

This $\mathfrak A$ and  $\mathfrak B$ agree on all formulas of rank $k+1$.

---
# References
[[Ehrenfeucht-Fraïssé Game]]
[[Quantifier rank]]
[[Rank-k Types]]