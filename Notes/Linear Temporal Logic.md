---
tags:
  - Note
  - Incomplete
---
202311171411

Tags : [[Logic]]
# Linear Temporal Logic
---
>[!hint] Motivation
>Classical Logic is really good for modelling structures that are static. That is, they do not change over time.
>But most real work structures are *dynamic*. They do change over time.
>*Temporal Logics* introduce operators that describe how the world changes without explicitly referring to time. This helps us guarantee properties like
>- Safety: Anything bad will not happen
>- Liveness: Something good will happen
>- Fairness: Evolution of subsystems

**Linear Temporal Logic** introduces operators with the assumption that time is *Linear*. There is one execution path of the "world" that is being talked about evolves on a given execution paths. 

---
## Syntax
**Linear Temporal Logic** is defined relative to a set of *primitive/atomic propositions* $\mathcal P$.

The set of formulas in **Linear Temporal Logic** can be given by the grammar
$$
\begin{align}
\varphi\quad:=\quad p\;&|\;\varphi\lor\varphi\;|\;\varphi\land\varphi\;|\;\lnot \varphi\;|\;\varphi \Rightarrow \varphi \\
&|\;\square \varphi\;|\;\diamond\varphi\;|\;\bigcirc \varphi\;|\;\varphi \cup\varphi
\end{align}
$$
Where the last $4$ operators are *temporal operators* which are supposed to be interpreted as 
- $\bigcirc f$  *Next $f$:* $f$ is true in the next state
- $\square f$ *Henceforth $f$:* $f$ will be true in all future states 
- $\diamond f$ *Eventually $f$:* $f$ is true at some future state
- $f\cup g$  *$f$ Until $g$:* $g$ will be true in some state in the future, $f$ is true in each state until then  

---
# References
[[Probabilistic Semantics for LTL]]
[[Topological Semantics for LTL]]
[[Semantics for LTL]]