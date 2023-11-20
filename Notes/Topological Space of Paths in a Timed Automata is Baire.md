---
tags:
  - Note
  - Incomplete
---
202311181411

Tags : [[Timed Automata]], [[Topology]]
# Topological Space of Paths in a Timed Automata is Baire
---
Let $\mathcal A$ be a [[Timed Automata Alternate Definition|timed automaton]] and $s$ be a state of $\mathcal A$ and let $\mathcal T_\mathcal A$ be a topology on $\text{Runs}(A,s)$. Then the topological space $\mathbb T=(\text{Runs}(\mathcal A, s),\mathcal T_\mathcal A)$ is a [[Baire Spaces|Baire Space]] 

## Proof
We proceed with proving that if we play the [[Banach-Mazur Games|Banach-Mazur game]] on the above topological space with $\mathcal T_\mathcal A$ as the family sets, and keeping a basic open set $\pi_\mathcal C = \pi_\mathcal C(s,e_1\dots e_n)$ as the target set(let $\pi$ be unconstrained version of $\pi_\mathcal c$).

That is we play $MB(\pi_\mathcal C,\text{Runs}(\mathcal A, s), \mathcal T_\mathcal A )$.

We show that Player 2 does not have a winning strategy for any open set as target and using 
![[Winning Strategy for Player 2 in Banach-Mazur games#^3923a6]]
this would show that none of the basic open sets of the space are meager. Hence the space is Baire.

We do that by showing a winning strategy exists for player 1.

We restrict the space to the path $\pi$. Because of how we have defined our topology, there is an embedding of $\pi$ in $\mathbb R^m$ for some $m\le n$.

The strategy for player 1 is:
- player one picks $\pi_1=\pi_{\mathcal C}$ 
Then we consider the embedding of $\pi_1$ in $\mathbb R^m$.

Now the game is equivalent to one where the space is $\mathbb R^n$, The target is a basic open set and the basis is the family of sets the gamed is played on. Also we have 

![[Winning Strategy for Player 1 in Banach-Mazur games#^305cd2]]
Thus, Player 1 has a winning strategy.


---
# References
