---
tags:
  - Note
  - Incomplete
---
202311172311

Tags : [[Topology]]
# Winning Strategy for Player 2 in Banach-Mazur games
---
>[!tip] Winning Condition
>There exists a *winning strategy* for player 2 iff $X$ is meager 

^3923a6

The goal for player $2$ is to make the intersection of the sets with $X$ empty. Hence it is natural to ask how *'small'* should a set be to ensure her victory.

A set is called *meager* if it is a countable union of *nowhere-dense sets*
Since $X$ is meager. Let $X$ be the union of the sequence $\{ S_{i} \}$ of nowhere-dense sets.

Since $S_i$ is nowhere-dense. Given any open set $O$, we can find an open set $O'\subseteq (O\cup S_i^c)$. This gives an open set that does not intersect with $S_i$.

This gives us the following strategy for the $i^{\text {th}}$ move for player 2
- If $\text{Int}(W_{2i-1}) \cap S_{i}=\emptyset$  then arbitrarily pick $W_{2i}$.
- Otherwise, let $O$ be an open set in the $W_{2i-1}$ that does not intersect with $S_i$ and pick an $W_{2i}$ inside $O$.
using this idea, we have made sure that $S_i$ will not intersect with $W_{2i}$.

Using the above strategy on each step gives us that for all $i\in\mathbb N$ we have $S_i\cap W'=\emptyset$ as $S_i\cap W_{2i}=\emptyset$ and $W'\subseteq W_{2i}$
Hence $X\cap W'=\emptyset$ and player $2$ wins.

---
# References
[[Banach-Mazur Games]]
[[Winning Strategy for Player 1 in Banach-Mazur games]]