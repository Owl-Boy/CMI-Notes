---
tags:
  - Note
  - Incomplete
---
202401031401

Tags : [[Combinatorial Optimisation]]
# Combinatorial Optimisation
---
Combinatorial Optimisation problem has a ground set $E$, solution set $\subseteq 2^{E}$.
**Goal:** obtain a solution of min/max wt where there is a wt function defined on $E$, eg. minimum spanning tree

## NP Optimisation Problems
---
An NPO $Q$ has the properties:
1. In polytime, we can determine if an input is a valid instance of $Q$.
2. For any instance $I$ of $Q$, there is a set of solutions $\text{sol}(I)$, $\forall s \in \text{sol}(I), |s|=\text{poly}(|I|)$.
3. Given $I,s,$ there is a polytime algo to check if $s \in \text{sol}(I)$.
4. There is a function $\text{val}$ that assigns a value to each $s \in \text{sol}(I)$ and $\text{val}(S)$ is polytime computable.

> [!info] Assuming $\text{P}\neq \text{NP}$, there are NPO problems whose opt solutions are not computable in polytime.


### Network flows
---
We know the max flow - min cut theorem which can be used to get a mincut, using the Ford-Fulkerson's algo.

> [!question] But what insight do we get from the theorem itself, if we forget about the algo for a while?

A problem $\in \text{NP} \cap \text{co-NP}$ implies:
1. There is a hope of getting a polytime algo
2. It is unlikely to be NP-complete (or co-NP complete) since that would imply NP = co-NP.

The constraint matrix for max flow is *totally unimodular* (TUM).
1. There exists an integral max-flow.
2. There exists a polytime algo for max-flow.
3. Max-flow min-cut theorem
4. Even for lower bounds, the LP gives a polytime algo and an integral max-flow, as well as min-cost max-flow in polytime.


### Matchings
---
A [[Matching Problem|matching]] is a subset of edges such that no two edges in the subset share an endpoint.
For bipartite graphs, Konig's theorem gives us that |max matching| = |min vertex cover|.
For non bipartite, not necessarily true, take a triangle for an example.

---
# Index
1. [[Combinatorial Optimisation]]
2. [[LP algorithm for Bipartite Matching]], Augmenting path algorithm
3. [[Edmond's algorithm for general Matching]]
4. [[Linear Programming]] and stuff about polyhedra
5. 


---
# References
