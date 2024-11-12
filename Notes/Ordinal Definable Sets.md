---
tags:
  - Note
  - Incomplete
---
202411031211

Tags : [[Set Theory]]
# Ordinal Definable Sets
---
>[!tip] Informally
>A set $a$ is order definable iff it is definable from some finite sequence of ordinals, i.e, there is a property $P(y_{1}\dots y_{n}, x)$ such and ordinals $\alpha_{1}\dots \alpha_{n}$ such that 
>$$ 
>\forall x(P(\alpha_{1}\dots \alpha_{n}, x) \leftrightarrow 
 x = a)
>$$
 
But this falls into the same trap and paradoxes as "the smallest non-definable set", to counter that, we make sure that only valid properties are being used by 
- Using [[Definable Formulas]]
- Using the [[Reflection Theorems]] to keep the size of the set in check

>[!definition] Ordinal Definable Sets $\mathbf{OD}$
>$\mathbf{OD}$ is the class of all sets $a$ such that
>- $\exists \beta> \text{rank}(a)$
>- $\exists n\in \omega$
>- $\exists s\in \beta^n$
>- $\exists R\in \text{Df}(R(\beta), n+1)$ such that
>
>$$ \forall x \in R(\beta)(x:s \in R \leftrightarrow x= a)$$



---
# References
