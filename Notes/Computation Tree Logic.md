---
tags:
  - Note
aliases:
  - CTL
---
c202404151204

Tags : [[Logic]]
# Computation Tree Logic
---
>[!tip] Motivation
>[[Linear Temporal Logic|Linear Temporal Logics]] give a very clean language to talk about properties of systems that evolve with time, but they are restricted to properties that universally quantify over all runs of a system.
>
>A program makes choices during its execution, hence there is a need to have a logic that quantifies existentially and universally over specific subsets of the runs (corresponding to choices).
>
>Branching Time Logics like *Computational Tree Logic* are a collection of logics that can do that.
>
>Algorithms for *CTL* also happen to be significantly simpler than algorithms for *LTL* 

**Computational Tree logic** talks about infinite unfoldings (that is where the **Tree** comes from) of a [[Kripke Models]] instead of an infinite run over it, and it has operators for quantification of runs on such unfoldings.

---
## Syntax
**Computational Tree Logic** is defined relative to a set of *primitive/atomic propositions* $\mathcal P$.

The set of *well formed* formulas in **Computational Tree Logic** is the language accepted by the following grammar:
$$
\begin{align}
\Psi &  & := &   &  &  p\;|\;\lnot \Psi\;|\; \Psi \lor \Psi\;|\;E\ \Pi\;|\; A\ \Pi \\
\Pi &  & := &   & & \Psi\;|\; X\ \Pi\;|\;\Psi\ \mathcal U\ \Psi
\end{align}
$$
Here the set of formulas is divided into a collection of *state formulas* represented by $\Psi$ and *path formulas* represented by $\Pi$.

>[!attention] Note
>It is not possible to nest path formulas using the until operator.

### Abbreviations
Some useful state formula abbreviations
- $EG\;\psi$
	- This states that there is a run from the current state where $\psi$ is always true.
	- This is short for $E \lnot(\textbf{true}\;\mathcal U\;(\lnot \psi))$
- $AG\; \psi$ : Analogous to the above definition.
- $EF\;\psi$
	- This states that there exists a run where $\psi$ we true at some point.
	- This is short for $E(\mathbf{true}\;\mathcal U\; \psi)$.
- $AF\;\psi$ : Analogous to the above definition.

---
# References
[[Semantics for CTL]]
[[LTL vs CTL]]