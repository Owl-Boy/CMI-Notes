---
tags:
  - Note
  - Incomplete
---
202401181301

Tags : [[Automata Theory]]
# Rabin Automata
---
A *Rabin Automata* is an $\omega-$Automata just like the [[Büchi Automata]]. It is similar to it except for the acceptance condition.

A *Rabin Automata* is a tuple $(\mathcal A, S)$ where $\mathcal A$ is a [[Transition  System]] and $S$ is a set of pairs of states $(G_i, R_i)$ of $\mathcal A$,

A word $w$ is accepted by the automata if there exists and $i$ and a run $r$ of the word $w$ where we visit $G_i$ infinitely many times and we only visit $R_i$ finitely many times.

---
# References
- [[hat V- Deterministic Büchi Automata]]
- [[Motivation for Rabin Automata]]
- [[Omega-Regular Languages]]