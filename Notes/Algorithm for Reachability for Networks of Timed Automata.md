---
tags:
  - Note
  - Incomplete
---
202310101410

Tags : [[Timed Automata]]

---
# Algorithm for Reachability for Networks of Timed Automata
Consider this [[Train Track Crossing for Timed Automata|Example]]. It shows that having a Reachability Axiom is Important for software verification purposes. 

```ad-warning
title: Region Automata is Too Inefficient!
Lets say we have a Network of 10 Timed Automata, and each of these have 10 states. All of them have a single clock and the maximum number present guards of all of the automata is 2.

A naïve way would be to first construct a [[Monolithic Timed Automaton for a Network of Timed Automata|Monolithic Automata]] which accpets the same language.

The above construction gives $10^{10}$ states, with 10 clock and guards having the maximum number $2$.

The time bound that for Region automata construction would give time around $10!\cdot 2^{10}\cdot 10^{10}$. Doing a reachability check in this automata is not feasible. A better approach is required
```


---
# References
