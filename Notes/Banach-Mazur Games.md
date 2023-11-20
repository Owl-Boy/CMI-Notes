---
tags:
  - Note
  - Incomplete
---
202311172211

Tags : [[Topology]]
# Banach-Mazur Games
---
>[!info] 
>A *Banach-Mazur* game is a 2-player game where the players try to pin down points in a space. The concept is closely related to [[Baire Spaces]].
>It was the first infinite game *positional game* with *perfect information* to be studied.
>It was introduced by **Stanisław Mazur** as the 43rd problem in the [[Scottish Book]] and the problem was solved by **Banach**.

---
## Setup
The game requires 3 things to be played
- A *topological space* $Y$
- A subset $X\subseteq Y$
- A family of subsets of $Y$ called $\mathcal W$ which has the following property
	- Each member of $\mathcal W$ has a non-empty interior
	- Every non-empty open set of $Y$ contains a member of $W$

A *Banach-Mazur* game is denoted by $MB(X,Y,\mathcal W)$

---
## Gameplay
Starting with player 1, each player a sequence of members of $\mathcal W$ that are contained in the previous one to form a chain of sets like 
$$
W_{0}\subseteq W_{1} \subseteq\dots
$$
Given any $W_i$, we know that it has a non-empty interior. So the next player can find an open set $O\subseteq W_i$. Then she can find $W_{i+1}\subseteq O$, hence the game will not terminate in a finite number of steps.

---
## Winning Conditions
Player 1 wins if $W' \cap X\ne\emptyset$ where $W' = \bigcap_{i\in\mathbb N}W_i$ 
Otherwise, Player 2 wins.

- There exists a [[Winning Strategy for Player 2 in Banach-Mazur games]] iff $X$ is *meager*. ^972715
- If $Y$ is a complete metric space, then there exists a [[Winning Strategy for Player 1 in Banach-Mazur games]] iff $X$ is *large* in some non empty open subset of $Y$.
---
>[!info] 
>The question that Mazur added to the book was that the above conditions are the only conditions where the game is determinable and a winning strategy exists.


---
# References
[Wikipedia](https://en.wikipedia.org/wiki/Banach%E2%80%93Mazur_game?useskin=vector) 