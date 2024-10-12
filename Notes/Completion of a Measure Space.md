---
tags:
  - Note
  - Incomplete
---
202409171809

Tags : [[Measure Theory]]
# Completion of a Measure Space
---
Given a measure space 
$$
\mathfrak M = (\Omega, \mathcal A, \mu)
$$
we have a measure $\mu$ only on subsets of $\Omega$ as defined by $\mathcal A$ but given that we want supersets to have bigger measures than smaller sets, we can assume the measure for some more sets in the following manner:

let $A \subseteq B$ where $A, B \in \mathcal A$ and $\mu(A) = \mu(B)=a$, then for every set $A \subseteq C \subseteq B$ then we would want $\mu(C)=a$

So we define that measure of all subsets of measure $0$ elements is $0$ and we construct the following space.

$$
\overline{\mathfrak M} = (\Omega, \overline{\mathcal A}, \overline\mu)
$$
Where
- $\overline {\mathcal A} = \{A\triangle I : A\in\mathcal A, I\subseteq B \text{ for some measure 0 } B\}$
- $\mu(A\triangle I) =\mu(A)$ where $I$ is subset of some measure $0\ B$

This is called the completion of the measure.

---
# References
