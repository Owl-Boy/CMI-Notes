---
tags:
  - Note
  - Incomplete
---
202401221201

Tags : [[Automata Theory]]
# $\omega$-Automata 
---

>[!tip] Variety
>$\omega$-Automata are a set of variants of [[Finite State Automaton]] that runs on infinite words. Since the acceptance condition for these automata cannot be the state at which the computation terminates (because it does not) there are a variety of accepting conditions and good states, some of them are listed below.

- **Buchi Automata** 
	- There is one set of good states $G$.
	- A word is accepted if there is a run of the word on the automata that goes the set $G$(any one) infinitely many times.
- **Rabin Automata** 
	- There is a sequence(typically finite) of pairs of set of good and bad states $\langle G_i, B_i\rangle$
	- A word is accepted if there is a run on the automata such that for some $i$ for which $G_i$ is visited infinitely many times and $B_i$ is visited only finitely many times.
- **Muller Automata** 
	- There is a family of subset of the states.
	- A word is accepted if there is a run such that the set of states visited in the run infinitely many times is exactly one of the members of the family.
- **Streett Automata**
	- This is dual condition for **Rabin Automata**
	- There is a sequence of pairs of sets of good and bad states
	- A word is accepted if for all $i$, either $G_i$ is visited infinitely often or $B_i$ is visited finitely often.
- **Parity Automata**
	- Here all the states are labelled a unique number from $0\dots n-1$
	- A word is accepted if there is a run where the smallest state which is visited infinitely often is even.

---
# References
