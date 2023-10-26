---
tags:
  - Note
---
202310132310

Tags : [[Timed Automata]]

---
# Simulation for Zone Automata
---

```ad-tldr
In this approach we give a preorder between _symbolic states_ and we modify $\text{Trans}$ rule to not add an elment $q$ if we have aleady reached an element $p$ such that $p\succeq q$.

We the prove that this operation is finite, i.e, for all sequences $(q,Z_{1}), (q,Z_{2})\dots$, we have $(q,Z_{j})\preceq(q,Z_{i})$ if $i\le j$.
If the preorder is finite, then the forward analysis always terminates.
```

A *Simulations* between two _Symbolic States_ of the transition system $\mathcal S$ is a relation $(q, v)\preceq(q',v')$ if
- $q=q'$
- If $(q,v)\rightarrow^{\delta}(q,v+\delta)\rightarrow^{t}(q_{1},v_{1})$ then there exists $\delta'$ such that $(q,v')\rightarrow^{\delta'}(q,v'+\delta')\rightarrow^{t}(q_{1},v'_{1})$ such that $v_{1}\preceq v_{2}$
Also shown by the diagram
![[Pasted image 20231019190459.png|400]]

The relation says, that if $a\preceq b$ then any transition that can be taken by $a$ can also be taken by $b$, but they might have to wait a different amount of time.

We extend the following definition for sets of valuations $W$ and $W'$
We say $(q, W)\preceq(q', W')$ if for every $a\in W$ there exist $a'\in W'$ such that $(q, a)\preceq(q, a')$.

Simulation relations are trivially *relfexive* and *transitive*.

---

Now, with simulation relations in our toolbelt, we can slightly change the [[Reachability Algorithm for Zone Automata#The naïve algorithm|the naive algorithm]] to get

![[Pasted image 20231019192110.png]]

where the only change is converting $Z\subseteq Z'$ to $(q, Z)\preceq(q, Z')$ in line 18
The proofs for *Completeness* and *Soundness* are almost identical to the one in the naive case.

---
## Finite Simulation

Currently we use subset relation as the simulation which does not terminate. We need to find a *Finite Simlution*
```ad-note
title: Finite Simulation
A _Simulation Relation_ is called *Finite* if there exists a number $K\in\mathbb N$ such that in every run of length more than $K$ that is 
$$
s_{0}\rightarrow s_{1}\rightarrow\dots\rightarrow s_{k}
$$
 there will be $i < j\le K$ such that $s_{j}\le s_{i}$
```
If we do this, then we guarantee that the program terminates!

## Simulation from region equivalence
Here we give a *simulation* relation that is finite, and which can be checked efficiently.

Given an Automaton, Let $M$ be the maximum bounds function and we say $v_{1}\sim_{M}v_{2}$ if $v_{1}$ and $v_{2}$ are region equivalent, then we define the relation
$$
(q, v_{1}) \preceq_{M} (q, v_{2})\quad\text{if}\quad v_{1}\sim_{M} v_{2}
$$
We know that this relation is finite, because for any given automata, there are only finitely many zones.

To extend this for sets of valuations, we define $\textbf{Closure}_{M}$. Let $W$ be a set of valuations. Then:
$$
\textbf{Closure}_{M}(W)\;:=\;\{v\;|\;\text{exists $v'\in W$ such that } v\sim_{M}v'\}
$$
Or, it is the union of regions intersecting $W$.

And we define $\sqsubseteq_{M}$ to be a relation on sets of valuations defined as 
$$
(q, W)\sqsubseteq_{M}(q, W')\text{ if } W\in\textbf{Closure}_{M}(W')
$$
The following relation is Finite, because the number of sets of regions in finite for any Automaton.

---
# References
[[Naive Algorithm for Reachability in Zone Automata]]
[[Reachability Algorithm for Zone Automata]]