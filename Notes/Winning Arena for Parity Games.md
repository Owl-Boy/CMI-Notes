---
tags:
  - Note
  - Incomplete
---
202403201203

Tags : [[Games on Graphs]]
# Winning Arena for Parity Games
---
>[!tldr] Goal
>Given a parity game, we want to split the arena into 2 parts denoting the winning region for Rajnikant and Sreevani.
>

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

---
# References
