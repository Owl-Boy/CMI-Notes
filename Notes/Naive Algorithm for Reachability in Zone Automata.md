---
tags:
  - Note
---
202310192010

Tags : [[Timed Automata]]

---
# Naive Algorithm for Reachability in Zone Automata

## The Algorithm

*Input:* Timed Automata $\mathcal A$ 
*Output:* `Yes` if any of the accepting states is reachable from the start state and `No` otherwise

![[Pasted image 20231019023024.png]] ^a9400a

---
## Correctness of the Algorithm
The above algorithm does not compute the entire zone graph, it does some optimizations to reduce the search space by not considering zones that already covered by a *Passed* node.

---
```ad-note
title:Soundess
If the algorithm finds a path from starting state to one of the final states, then there will be a corresponding path in the timed automata.
```

This is because every transition suggest by the algorithm corresponds to a transition in the Zone Automaton, and reachability in Zone Automaton implies reachability in the corresponsing Timed Automata.

---
```ad-note
title:Completeness
Let $\rho:=(q_{0},v_{0})\xrightarrow{\delta_{0},t_{0}}(q_{1},v_{1})\xrightarrow{\delta_{1},t_{1}}\cdots\xrightarrow{\delta_{n-1},t_{n-1}}(q_{n}, v_{n})$  be a run on the Timed Automata to one of the final states where $q_{0}\dots q_{n-1}$ are not final states and $q_{n}$ might or might not be one. Then for each configuration in the run, there is a a node $(q_{i},Z_{i})$ such that $v_{i}\in Z_{i}$
```

Proof is by Induction on length of run to $(q_{n}, v_{n})$

**Base Case**
We know that $v_{0}\in Z_{0}$. And when the loop is entered for the first time, $(q_{0}, Z_{0})$ is added to the $\text{Passed}$ list.

**Induction Step:**
Assuming that for each configuration in run given above upto $(q_{n-1},v_{n-1})$ we have a corresponding _symbolic state_ in the $\text{Passed}$ list. 
As $(q_{n-1}, Z_{n-1})$ is in $\text{Passed}$, any transition that can be taken form that zone, will be put in the $\text{Waiting}$ list. Which includes the $\tau:=(q_{n-1},v_{n-1})\xrightarrow{\delta_{n-1},t_{n-1}}(q_{n},v_{n})$.
Since it a possible transition, we have $Z_{n}=\text{Post}_{\tau}(Z_{n-1})\ne \emptyset$ hence $(q_{n},Z_{n})$ will be put in the $\text{Waiting}$ list. Which will then be passed if there isn't $(q_{n}, Z_{n}')$ such that $Z_{n}\subseteq Z_{n}'$. In which case we will already be done.

---
Although we did show that our algorithm is *Complete* and *Sound*, this does not mean that our algorithm will terminate.

```ad-warning
title: Non-termination
There exists a Timed Automata for which the above algorithm might not terminate.
```

Consider the following Timed Automata
![[Pasted image 20231019021126.png]]
This has two clocks and no accepting state.
The Zone after when the transition is taken from $q_{0}\to q_{1}$ can be given by $x=y$ which of the form $x-y=k$ with $k=0$. For every Zone of such form, we get that the transition from $q_{1}$ can be taken and it gives the zone $x-y=k+1$. Hence the program does not terminate.

---
# References
[[Simulation for Zone Automata]]
[[Reachability Algorithm for Zone Automata]]