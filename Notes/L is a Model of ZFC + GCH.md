---
tags:
  - Note
  - Incomplete
---
202411102211

Tags : [[Set Theory]]
# L is a Model of ZFC + GCH
---
After showing that choice holds in $\mathbf{L}$ in [[L is a Model of ZFC]], we now move to $\text{GCH}$. 

Let $\chi$ be a finite conjunction of axioms of $\text{ZF}+\mathbf{V}=\mathbf{L}$ such that 
$$
\forall M(M \text{ transitive } \land \chi^M \to M = L(o(M)))
$$
Assume $\mathbf{V}=\mathbf{L}$ and fix $A \in \mathcal P(L(\alpha))$ and let $X = L(\alpha) \cup A$ then $|X|=|\alpha|$. My [[Löwenheim-Skolem and its Variants|Lowenheim-Skolem]] there is  a model $M$ such that $|M|=|\alpha|$, my Mostowski Collapse, we can make it transitive. $X \subseteq M$ and $\chi^M \leftrightarrow \chi^V$.  So $M=L(o(M))$, but since $|M| = \alpha$, we have $|o(M)| < \alpha^+$. Thus 
$$
A \in L(o(M)) \subseteq L(\alpha^+)
$$

This makes proving the following easy
>[!theorem] $\mathcal P(\alpha)=\alpha^+$

To prove this we have $|\alpha|=|L(\alpha)|$ therefore $2^{|\alpha|}=2^{|L(\alpha)|}\leq |L(\alpha^+)|=|\alpha^+|=\alpha^+$
And we have that $2^\alpha \geq \alpha^+$ by cantor, hence proved. This gives us the straightforward corollary

>[!theorem]
>$\models \text{Con(ZF)} \to \text{Con(ZFC+GCH)}$

---
# References
