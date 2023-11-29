---
tags:
  - Note
---
202311291411

Tags : [[Logic]]
# Natural Numbers with Successor
---
We define the following language on $\mathbb N$
$$
\mathfrak N_{S} = (\mathbb N;\mathbf{0}, S)
$$
The axioms that will be used in the theory are
1. $\forall x\mathbf S x \ne 0$, A sentence asserting that $0$ does not have a predecessor
2. $\forall x\forall y(\mathbf S x\equiv \mathbf S y \to x \equiv y)$. The successor function is injective
3. $\forall y (y\ne \mathbf 0 \to \exists x (y = \mathbf S x))$. Every non-zero number has a predecessor
4. Successor applied multiple times never gives back the arguement
	-  $\forall x \mathbf Sx\ne x$ 
	-  $\forall x \mathbf S^2x\ne x$ 
	-  $\dots$
	- $\forall x \mathbf S^n x \ne x$

Let the above set of axioms be called $A_S$ and since all of them are trivially true in $\mathfrak N_S$, we have 
$$
\text{Cn}\; A_{S}\subseteq \text{Th}\;\mathfrak N_{S}
$$
where 
- $\text {Cn}$ is the set of formulas that can be derived using the axioms (which will  all be sentences as axioms are sentences)
- $\text {Th}$ is the set of sentences that are true in a theory.

What isn't easy to show is that $\text{Cn}\ A_S = \text{Th}\ \mathfrak N_S$. i.e [[Natural Numbers with Successor Function is Complete]]

---
# References
[[Quanitifier Elimination for Natural Numbers With Successor]]
[[Natural Numbers with Successor Function is Complete]]
[[Decidability of Presburger Arithmetic]]
[[Natural Numbers with Successor and Ordering]]