---
tags:
  - Note
  - Incomplete
---
202404061504

Tags : [[Games on Graphs]]
# Winning Arena for Rabin Games
---
>[!tldr] Plan
>We start with the base case of 1 pair of good and bad sets, and then we extend the solution for a general rabin game.

---
## Simple Case - 1 pair of sets
In this case, we want to visit some good state $G$ infinitely many times, without visiting the bad state $B$ infinitely many times. 

- We first ensure that we do not visit $B$ infinitely many times as follows.
	- We restrict the game to the trap $A = V \setminus \text{Attr}_E(V, B)$
- Now inside $X$ we visit $G$ infinitely many times so we do the same process as discussed in [[Winning Arena for Parity Games]] to get the winning set $Y$ in $X$
- We end it by extending the strategy to the entire arena by
	- $W_E = \text{Attr}_{E}(V, Y)$ 

---
## General Case
For the general case we want our rabin game to have a chain condition which is as follows
$$
B_{1} \subsetneq G_{1} \subsetneq B_{2} \dots \subsetneq G_{n}
$$
Any Rabin game can be converted to an equivalent Rabin Game with this condition by converting it to a Muller game and then back to a Rabin Game.

For such games we can find ***Elster***-paradises for each pair separately and then take their union which gives the largest ***Elster***-paradise.

>[!info] Proof Sketch
>From any point outside the final ***Elster***-paradise ***Adler*** can either force the game to stay away from $G_n$ after a finite time or can force to stay inside $B_n$ and in the second scenario we make the same argument for level $n-1$. Therefore the complement of that paradise is a ***Adler***-paradise.

>[!caution]
>The Chain condition is important for the proof to work, it is discussed more in [[Winning Arena for Rabin Games - Fail]].

---
# References
[[Winning Arena for Parity Games]]
[[Winning Arena for Büchi Games]]
[[Winning Arena for Rabin Games - Fail]]