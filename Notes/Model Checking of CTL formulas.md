---
tags:
  - Note
  - Incomplete
---
202404171204

Tags :[[Logic]]
# Model Checking of CTL formulas
---
- Some Fragment (SNF lol)
	- $\Psi := T | p | \lnot \Psi | \Psi \lor \Psi | E X \Psi | E(\Psi U \Psi) | E G \Psi$
- We do model checking by finding the set of states that satisfy the formula
	- All states satisfy T
	- Labelling function directly tells if a state satisfies a proposition
	- S(not Psi) = complement of S(Psi)
	- S(A or B) = S(A) union S(B)
	- S(E X Psi) = {S | post S intersetciont S(Psi) = non-empty}
	- S(E (A U B)) = S(B) and any state that satisifes A and can go to B, fix point of that
	- S(E G A) = take all states, remove those that do not satify A, then we remove element whose children are not in A and do that repeatedly.

Mu calculus :  Based on Fixed points. Very Complicated. 


---
# References
