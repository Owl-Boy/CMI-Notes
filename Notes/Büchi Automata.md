---
tags:
  - Note
---
202401041201

Tags : [[Automata Theory]]
# Büchi Automata
---
A *Büchi Automata* is a modification of a [[Finite State Automaton]], so that it can accept infinite words.

A *Büchi Automata* is a tuple $(\mathcal A,G)$ where $\mathcal A$ is a [[Transition  System]] and $G$ is a set of good states. 

A word $w$ is accepted by the automata if it has a run that goes over good states,  infinitely many times.

>[!attention] determinism is weaker
>Example Language $L=\{w| \text{only finitely many a's in }w\}$ where the alphabet is $\{a,b\}$
>**Proof**: We construct a word in the following manner.
>- We keep reading $b$'s until we reach a good state, then we read an $a$ and $b$'s again until we reach another good state. We keep doing that until one of the good states is repeated, and we pump that section giving a word with infinite number of $a$'s that is accepted by the automata.
>- We also can get to a new state because at any point, if we decide to stop and just accept $b$'s we get an accepted word, so a sequence of $b$'s must take us to a good state in finitely many steps.
>
>This weakening makes sense because the powerset construction just holds the information about the states that can be reached. You necessarily lose power about the set of sub-runs and where those can reach.
>This is fine for a finite automata, because acceptance only depends on reachability.
>For a Büchi Automata, the path taken, i.e the run itself matters, hence the powerset construction does not carry enough information to keep the same automata.

---
# References
- [[Language of Infinite words]]
- [[Set of Languages accepted by Büchi Automata are exactly Omega-Regular]]
- [[Omega-Regular Languages]]
- [[Rabin Automata]]