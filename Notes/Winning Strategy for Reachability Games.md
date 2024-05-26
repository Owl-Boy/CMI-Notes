---
tags:
  - Note
---
202403241003

Tags : [[Games on Graphs]]
# Winning Strategy for Reachability Games
---
## Elster
For player ***Elster***, if the vertex belongs to $A_E$, it belongs to some $\mathcal A_{E}(i)$ and not in $\mathcal A_{E}(i-1)$, but it has an edge to it.
So ***Elster*** chooses to go to a vertex in $A_E(i-1)$. By construction, ***Adler*** is forced to go to $\mathcal A_E(i-2)$. This process must terminate at $\mathcal A_E(0)$.
![[Elster Winning strat.excalidraw]]

## Adler
If some vertex belongs to $\mathcal A_A$ then it does not belong to any $\mathcal A_E(i)$. 
This means it does not belong to `pre(A_E(i))`. Hence, its ***Elster***'s turn, he cannot go to any $\mathcal A_E(i)$ and if its ***Adler***'s turn, she can choose to stay away from $\mathcal A_E(i)$. Thus the game never goes to the target node $x$.

![[Adler Winning Strat.excalidraw]]

>[!attention] Proof is omitted as its kinda trivial

---
# References
[[Winning Arena for Reachability Games]]
[[Winning Arena for Büchi Games]]
[[Winning Strategy for Büchi Games]]