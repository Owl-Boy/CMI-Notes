---
tags:
  - Note
---
202311291711

Tags : [[Logic]]
# Natural Numbers with Successor and Ordering
---
We define the following structure
$$
\mathfrak N_{L}\quad := \quad (\mathbb N;\mathbf{0},\mathbf{S},<)
$$
The theory of this structure is decidable because it also admits [[Quanitifier Elimination for Natural Numbers With Successor#^411d8b|quantifier elimination]]. But it is finitely axiomatizable and not categorical in any infinte cardinality.

The following are a set of axioms for the arithmetic
- $\forall y (y\not\equiv 0\to \exists x(y=\mathbf{S}x))$ Every non zero number has a predecessor.
- $\forall x\forall y(x<\mathbf S y\leftrightarrow x\le y)$
- $\forall x (x\not<\mathbf 0)$ 
- $\forall x\forall y(x<y \lor x\equiv y\lor y<x)$, trichotomy
- $\forall x\forall y (x<y \to y\not<x)$, antisymmetry
- $\forall x\forall y\forall z (x<y\to (y<z\to x<z))$, transitivity

let the set of axioms be called $A_L$, and we still have that all axioms are true in $(\mathfrak N_L)$ so we again have $\text{Cn}\;(A_L)\subseteq\text{Th}\;\mathfrak N_L$. The inclusion in the other direction is true but not obvious.

We can prove it by showing [[N_L admits Quantifier Elimination]]

This gives us that $\text{Cn}\; A_L$ is complete, and $\text{Cn}\;A_L=\text{Th}\;\mathfrak N_L$. 
This $\text{Th}\;\mathfrak N_L$ is also decidable.

---
# References
[[N_L admits Quantifier Elimination]]
[[Decidability of Presburger Arithmetic]]