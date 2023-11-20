---
tags:
  - Note
  - Incomplete
---
202311190011

Tags : [[Theory of Computation]], [[Logic]]
# PSPACE-Hardness of LTL Model Checking
---
## Proof sketch

For a [[Turing Machines|TM]] that is bounded by $S(n)$ which is a polynomial on $n$, then for a know input $a=a_{1}\dots a_{n}$ we construct an [[R-Structure]] That looks like 

![[Pasted image 20231119003001.png]]

let $\mathcal P = Q\times\Sigma\sqcup\Sigma\sqcup\{\text{BI},\text{EI}\}$
Where we have $S(n)$ diamonds and for each diamond we have $|Q\times\Sigma\sqcup\Sigma|$ vertical vertices and on each vertex one of the propositions true.
A path from $\text{BI}\to\text{EI}$ encodes an instantaneous discription of a turing machine.

We use LTL formulas to represents relations between configurations of the turing machine in each step, accepting conditions are trivial.

---
# References
