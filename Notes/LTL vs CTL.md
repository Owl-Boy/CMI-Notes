---
tags:
  - Note
  - Incomplete
---
202404161904

Tags : [[Logic]]
# LTL vs CTL
---
Both [[Linear Temporal Logic|LTL]] and [[Computation Tree Logic|CTL]] are temporal logics commonly used a languages for writing specification. This begs the question: Which is better?  

>[!definition] What is better
>Better in this context means more expressive, since both formulas are defined for [[Kripke Models|Kripke Structures]], using those as a comparison metric seems useful
>
>We will say that one of the logics is more expressive than the other if give any  $2$ structures $K_1$ and $K_2$, one of them will be able to distinguish between them and the other one won't
>

>[!attention] Spoiler Alert : They are incomparible!

---
## CTL $\not\subseteq$ LTL

Consider the following Kripke Structures.
![[CTL not weaker than LTL.excalidraw]]
The CTL formula $p \implies (EX\ q \land EX \lnot q)$.
- This formula is satisfied by the left kripke structure but not by the right one.

LTL cannot distinguish between the two structures as the set of runs produced by both of them are the same.

---
## LTL $\not\subseteq$ CTL
Consider the following *LTL* formula $FG\ p$. This formula states that in each run of the kripke structure, there will be a point after which $p$ will be true in all states.

>[!tldr] TODO : EF Games for CTL 



---
# References
