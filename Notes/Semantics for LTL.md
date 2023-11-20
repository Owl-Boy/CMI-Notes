---
tags:
  - Note
  - Incomplete
---
202311172211

Tags : [[Logic]]
# Semantics for LTL
---
The *semantics* of an **LTL** formula is defined by a satisfaction relation 
$$
\models\; \subseteq(\mathbb N\to 2^\mathcal P)\times\mathbb N\times LTL
$$

To say$(\sigma, j, f) \in \models$ we write $(\sigma, j)\models f$ 

We can think of this as a sequence of worlds like a [[Kripke Models|kripke structure]] where $\sigma$ defines which world models which proposition and $j$ fixes a world to talk about $f$.

## Propositions
$$
(\sigma, j)\models p\quad\text{iff}\quad p \in\sigma(j)
$$
![[Pasted image 20231117151425.png]]
## Next
$$
(\sigma, j)\models \bigcirc p\quad\text{iff}\quad (\sigma,j+1) \models p
$$
![[Pasted image 20231117151610.png]]
## Henceforth

$$
(\sigma, j)\models \square p\quad\text{iff}\quad \forall k\cdot(k \geq j \Rightarrow (\sigma,k)\models p)
$$
![[Pasted image 20231117152033.png]]
## Eventually
$$
(\sigma, j)\models \diamond p\quad\text{iff}\quad \exists k\cdot(k \geq j \Rightarrow (\sigma,k)\models p)
$$
![[Pasted image 20231117152137.png]]
## Until
$$
(\sigma, j)\models f\cup g\quad\text{iff}\quad \exists k \cdot(k\ge j \Rightarrow(\sigma,k)\models g\quad \land\quad \forall i \cdot(j \leq i < k \Rightarrow (\sigma, i) \models f)
$$
![[Pasted image 20231117152206.png]]
## Boolean operators
These are defined in the usual manner
- $(\sigma, j)\models\lnot f\iff(\sigma, j)\not\models f$
- $(\sigma, j)\models f \lor g\iff(\sigma, j)\models f \lor(\sigma,j)\models g$
- $(\sigma, j)\models f \land g\iff(\sigma, j)\models f \land(\sigma,j)\models g$
- $(\sigma, j)\models f \Rightarrow g\iff(\sigma, j)\models f \Rightarrow(\sigma,j)\models g$

---
# References
- [[Linear Temporal Logic]]
- [[Probabilistic Semantics for LTL]]
- [[Topological Semantics for LTL]]
- [[Topology over Finite Paths in a Timed Automata]]