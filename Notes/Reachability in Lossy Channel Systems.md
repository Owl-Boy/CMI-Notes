---
tags:
  - Note
  - Incomplete
---
202310241510

Tags : [[Theory of Computation]], [[Timed Automata]]

---
# Reachability in Lossy Channel Systems

```ad-note
title: Lossy Channel Systems
A **Lossy Channel System** is like a [[Channel Systems|Channel System]] but on each transition, the channel can lose some of its letters(from any part of the work) and become a subword.
```

```ad-todo
- #### Encoding Channel runs as Timed words
	- Let configurations be $q_{i}, w_{i}$ and we say that $q_{i}$ is accepted at $n-i$.
	- between $q_{i}$ and $q_{i-1}$ we have the transition and word encoded in between them, and between two such encodings there is a distance of exactly 1 between corresponding letters
	- Then we have a one clock non deterministic timed automata for accepting invalid words, this can be done with 1 clock with non determinisitic automata
		- let q_i and $\gamma_i$ be incompatible, or;
		- Let there be any letter which does not appear 1 second later.
```

---
# References
