---
tags:
  - Note
  - Incomplete
---
202401221201

Tags : [[Automata Theory]]
# $\omega$-Automata Acceptance Conditions
---
- Buchi Automata : You have a set of good states, at least one of them should be visited infinitely many often.
- Rabin Automata :  You have paired up subsets of the states labelled good and bad an you need to find one pair where you visit the good part infinitely many often, and the bad part, just finitely many often.
- Muller Automata : You give a family of subsets of states, and the inf of the run should be exact one of the members of the family.




You have the normal automata, and the subset one.
When you take a transition in the normal one, you visit a state, 
- if it is a state you have already visited, then you do nothing in the subset one
- otherwise you change the state in the subset one which corresponds to adding the state to the set of states you have visited,
- We have a target set of states F, once we get to F, we go back to the empty collection so we can build back upto F
- This means we will visit all states in F infinitely many often

>[!todo]
>- This note
>- Note on Last action record construction 

---
# References
