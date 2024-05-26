---
tags:
  - Note
---
202403201203

Tags : [[Games on Graphs]]
# Winning Arena for Parity Games
---

>[!fail] Naive strategy that fails
>The most obvious thing that does work would be the combination of two of these kinds of startegy
>- A)Keep visiting infinitely many times : Which is just the Buchi strategy
>- B)Eventually never visit : Which can be constructed in the following way.
>	- Take the bad set. 
>	- Find its attractor
>	- Consider the complement of the bad set. This is the largest trap outside the bad set.
>	- The attractor of the that.
>
>Now our winning set would be $A(n) \cup B (n-1) \cup A(n-2)  \cup \dots$
>Which would just be, we go to least import sets good set but not the bad sets that have a higher priority, or next good set with least priority and so on.
>
>This strategy fails because consider a situation where we consider visit a set $G$ again and again, and visit $B$ only finitely many times. It might be that if we want to visit $G$ infinitely many times, all paths would go though $B$, but at the same time, it might be possible to completely avoid $B$ if we don't care about visiting $G$ infinitely often. 
>These kinda of paths will not be eliminated and hence we will have a faulty strategy.
>

## Stealing the Rabin Game Strategy
The Parity can be very easily be converted to a Rabin game as follows.
For each $n$
- let $G_n$ be the set of all vertices that have the colour $2n$
- let $B_n$ be the set of all vertices that have a colour of odd parity of size less than $2n$

Now we just use the strategy described in [[Winning Arena for Rabin Games]].

--- 
## Proof that Parity Games are Determined
>[!tldr] Plan
>Consider the largest ***Adler***-paradise, and show that it's complement is a ***Elster***-paradise

Let $X^A_{i}$ be a ***Adler***-paradise and consider all let $X^A = \bigcup_{i\in I}$ be the union of all ***Alder***-paradises which is the largest ***Adler***-paradise.

But since $\text{Attr}_A(X^A) \supseteq X^A$ and $\text{Attr}_E(X^A)$ is a ***Adler***-paradise, $X^A$ is its attractor, so the complement of $X^A$ is an ***Adler***-trap.

We now restrict the game to the trap defined above. In that sub-game let $S_0$ be the set of vertices that are coloured $0$. 

Now we consider the part of the sub-game that is the complement of $\text{Attr}_E(S_{0})$ which is a ***Elster***-trap. Now in that sub-sub-game the number of colours used are strictly less, so by induction we can show that there is a partition sub-sub-game which are ***Elster*** and ***Adler*** paradises.

- In the sub-sub-game, the ***Adler***- paradise gives a winning strategy for ***Adler***, which will work as long as ***Elster*** does not move the game to the set $X^A$ from which ***Adler*** again has a winning strategy, this again contradicts the maximality of $X^A$ therefore the entire arena of the sub-sub-game is a ***Elster***-paradise.
- The ***Elster***-paradise gives a strategy for ***Elster*** that can be used as long as ***Adler*** does not go out of the sub-sub-game to the set $Attr_E(S_{0})$. But if ***Adler*** does that, ***Elster*** can then visit a node with value $0$ and after that either stay in the attractor or go back to the sub-sub-game. $(X^A)^c$ is an ***Elster***-attractor.

![[Parity Games are determined.excalidraw|800]]

---
## Complexity of existence of a winning strategy in a finite-arena parity game.
>[!question] Problem
>Given a parity game $G$ and a vertex $v$ from the vertex set of $G$, can ***Elster*** force a victory.

>[!note] Complexity
>The problem is in [[NP (Complexity Class)|NP]] $\cap$ [[Co-NP (Complexity Class)|Co-NP]].
>This means that its highly unlikely that the problem is [[NP Complete]], but there is no known algorithm in [[P Complexity Class|P]] for the problem.

### NP Algorithm
>[!idea]
The Idea is to guess a strategy and to check if the strategy is winning in polynomial time.

We represent selecting a strategy by removing every outgoing edge from every $v\in V_E$ except for the one picked by the strategy, so our algorithm becomes as follows:
- We go to the description of each $v\in V_E$ and we remove all outgoing edges except for one that is picked that the strategy that was decided non-deterministically.
- In the reduced graph we now check that the strategy is correct by checking if there exists and odd-cycle in the same weakly-connected component as $v$.
	- This is done by doing a DFA from each vertex checking if there is a path from each vertex $v \in  V_A$ that comes back to $v$ and doesn't go over a vertex that has index less than that of $v$. 
	- This is used to detect a cycle with $v$ as the element with colour of least index. If we find one, then we halt the machine rejecting the input. otherwise we accept.

### Co-NP Algorithm.
Since the game is a zero-sum game without draws, if ***Elster*** cannot win, then ***Adler*** must be able to win. Hence, checking if ***Elster*** cannot win is the same as checking if ***Adler*** can win. 

We use the same algorithm discussed in the previous section by modifying to so it checks if ***Adler*** can win.

---
# References
[[Winning Arena for Büchi Games]]
[[Winning Arena for Reachability Games]]
[[sigma-paradise]]