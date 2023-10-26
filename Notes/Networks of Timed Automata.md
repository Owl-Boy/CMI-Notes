---
tags:
  - Note
---
202310101210

Tags : [[Timed Automata]]

---
# Networks of Timed Automata
```ad-tip
title:Motivation
In a lot of real world cases. There are multiple systems working together in sync with each other, acting as one organized structure.

The organized structure can get very complicated, and its often easier to model the smaller parts of the system that are then connected by constraints and relations. 

A **Network of Timed Automata** is a collection of Timed Automata, that run simultaneously to model different parts of a larger system. These parts of synced together by letters that are in common between the Automata. I interpret these are the same *stimulus* or *action* to/by multiple automata.

Although it is possible to model the entire **Network** with just a single _monolithic_ automaton. But that is often more complicated to work with.

This also demands the use for a new reachability algorithm (a lot of times to figure out if its possible to reach a problematic state which will be made clear in the examples) as the **Region Automata** idea is "absolutely infeasible".
```

A **Network of Timed Automata** is a set of _processes_ $\langle\mathcal A_{1},\mathcal A_{2},\dots\mathcal A_{k}\rangle$ running in parallel, that have alphabets $\Sigma_{1},\Sigma_{2}\dots\Sigma_{k}$ which _need not_ be _disjoint_, and a set of local clocks for each. That is $X_{i}\cap X_{j}=\emptyset$ whenever $i\ne j$.
Also, given that $a\in\Sigma_{i}$ and $a\in \Sigma_{j}$. The *Automata* $\mathcal A_{i}$ and $\mathcal A_{j}$ both must accept the letter at the same time (The letter is accept only when guards of both Automata satisfy).

```ad-example
title: Example of a Network
![[Drawing 2023-10-11 01.28.18.excalidraw]]

Here the Automata have the languages $\{a,c\}$ and $\{b, c\}$ respectively.

The language accepted by this is either `ab` or `ba` at time stamps $1\dots n-1$ and accept a $c$ at time $n$
```

To clarify on the *Synchronization* part, another interesting situation is when two automata from the network are in a configuration where only one of the automata can accept a common letter, then the entire network will come to a halt.

```ad-example
title: Network which does not accept due to synchronization problems

In the above example if we let the alphabet of the first automaton to be $\{a,b,c\}$ then the network cannot accept $b$, hence the Language of the network will be $\{c\}$
```

[[Train Track Crossing for Timed Automata|Here]] is a more non trivial example where a **Network** would be useful.

The Above example also shows the importance of having a fast Algorithm for Reachability for Networks of Timed Automata. One way to do its to it is to construct a [[Monolithic Timed Automaton for a Network of Timed Automata|Monolithic Timed Automaton]] and make its [[Zone Automata|Zone Automaton]], and check for reachability on it.

---
# References
[[Monolithic Timed Automaton for a Network of Timed Automata]]
[[Zone Automata]]
[[Train Track Crossing for Timed Automata]]
