---
tags:
  - Note
---
202404161904

Tags : [[Logic]]
# Semantics for CTL
---
The *semantics* for a **CTL** formula is defined by a satisfaction relation
$$
\models\; \subseteq\mathcal K\times\mathbb N\times LTL
$$
To say$(\sigma, j, f) \in \models$ we write $(\sigma, j)\models f$ and we let $\mathcal K$ to be the set of [[Kripke Models|Kripke Structures]].

For defining the relation, we first consider $(\sigma, j)$ as the infinite tree-unfolding of the *Kripke Structure* from the state $j$ and we say $(\sigma, j) \vDash f$ if the root of the tree satisfies the formula in the following manner.

- ***Atomic Propositions:*** $(\sigma, j) \vDash p \iff j \Vdash p$ 
- ***Boolean Operations:*** These are defined in the usual manner
	- $(\sigma, j)\models\lnot f\iff(\sigma, j)\not\models f$
	- $(\sigma, j)\models f \lor g\iff(\sigma, j)\models f \lor(\sigma,j)\models g$
	- $(\sigma, j)\models f \land g\iff(\sigma, j)\models f \land(\sigma,j)\models g$
	- $(\sigma, j)\models f \Rightarrow g\iff(\sigma, j)\models f \Rightarrow(\sigma,j)\models g$
- ***Path Operators:*** There are similar to the temporal operators from linear temporal logics and work on a fixed path, they are necessarily used in conjunction with existential or universal operator discussed later.
	- ***Next:*** After fixing a path $(\sigma, j)\models X\ p \iff(\sigma, \text{next}(j))\models p$
	- ***Until:*** Also similar to how it was defined in [[Linear Temporal Logic|LTL]] : There exists a state $k$ after $j$ in the run such that $(\sigma, j)\models p_1\ \mathcal U\ p_2 \iff (\sigma, j\dots k-1)\models p_{1}$ and $(\sigma, k)\models p_{2}$.
- ***Path Quantifies*** (for the lack of a better term) : These operators take in a state and a path formula and quantify that path formula on the set of runs starting from the state.
	- $E$ quantifies the formula existentially
	- $A$ quantifies the formula universally.

## Example
- ***Propositions*** : $\psi = p$
	- ![[CTL prop.excalidraw]]
- ***Path Quantifiers***
	- $\psi = EF\ p$
		- ![[Existential finally.excalidraw]]
	- $\psi = A (p_{1}\ \mathcal U\ p_{2})$
		- ![[Universal until ctl.excalidraw]]

---
# References
[[Computation Tree Logic]]