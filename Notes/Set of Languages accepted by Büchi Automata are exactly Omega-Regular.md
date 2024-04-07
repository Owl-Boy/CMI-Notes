---
tags:
  - Example
---

202401041557

tags : [[Automata Theory]]

---
>[!theorem] Set of languages accepted by a [[Büchi Automata]] are precisely [[Omega-Regular Languages]] 

To prove left to right:
A word is accepted by a [[Büchi Automata]] if there exists a run of the word in the automata that contains infinitely many good states. But since the automata only has finitely many states, it has finitely many good space. 
Hence, given a *Büchi Automata* we find the set of words from the start state(unique start state without loss of generality) to the good states, upto a certain size. That would be $U$, we let $U_i$ to be the subset of $U$ that ends at state $i$. 
Then we assume that the state we are in, is the state that repeats infinitely many times. So we let $V_i$ be the set of words that start and end at the particular good state. Hence the language of the *Büchi Automata* becomes the finite union.
$$
L=\bigcup_{i\in G} U_{i}\cdot V_{i}
$$
>[!tip] idea
>We reach a good state from the start state and that state keeps appearing infinitely many times in the run.

To prove right to left:
$\omega$-regular languages are closed under finite union, so we just need to make a *Büchi Automata* for $U\cdot V^\omega$ 

Given *DFAs* for $U$ and $V$, we make the following
- We start with $V^\omega$, given a *DFA* for $V$, we make an *NFA* such that there are no incoming transitions to the start state of it. Then for each edge going to the final state, we make a copy that goes to the start state, and make the start the only final state.
- For $U$, we make the *DFA*, and for every transition that goes to a final state, we make a transition that goes to the start state of *DFA* of $V$

---
# Related 
[[Büchi Automata]]
[[Omega-Regular Languages]]