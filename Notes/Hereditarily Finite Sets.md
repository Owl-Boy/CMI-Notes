---
tags:
  - Note
---
202409030509

Tags : [[Set Theory]]
# Hereditarily Finite Sets
---
>[!theorem]
>$x \in R(\omega) \iff x \in \text{WF} \land \text{trcl}(x)$ is finite

For $\to$
If $x\in R(\omega)$, then $x\in R(n)$ for some $n\in \omega$, hence $\text{trcl}(x)$ is finite.

For $\leftarrow$ 
let $n = \{\text{rank}(z) : z \in \text{trcl}(x)\}$. $n$ is finite. Rank $z < n$, therefore $x\subseteq R(n)$, therefore $x\in R(n+1)$.

---

>[!definition]
>$HF =R(\omega)$ is the set of *hereditarily finite sets*.

If we think of $\in$ as a directed graph and draw a picture of $x$ together with $\text{trcl}(x)$, then $x$ is the set of its children and $\text{trcl}(x)$ is the set of $x$ together with all its descendants of $x$, hence the name.

All of finite mathematics lives in $\text{HF}$.

---
# References
