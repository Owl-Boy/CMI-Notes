---
tags:
  - Note
  - Incomplete
---
202310101410

Tags : [[Timed Automata]]

---
# Zone Automata
Consider this [[Train Track Crossing for Timed Automata|Example]]. It shows that having a Reachability Axiom is Important for software verification purposes. 

```ad-warning
title: Region Automata is Too Inefficient!
Lets say we have a Network of 10 Timed Automata, and each of these have 10 states. All of them have a single clock and the maximum number present guards of all of the automata is 2.

A naïve way would be to first construct a [[Monolithic Timed Automaton for a Network of Timed Automata|Monolithic Automata]] which accpets the same language.

The above construction gives $10^{10}$ states, with 10 clock and guards having the maximum number $2$.

The time bound that for Region automata construction would give time around $10!\cdot 2^{10}\cdot 10^{10}$. Doing a reachability check in this automata is not feasible. A better approach is required
```

Much like [[Region Automata]], **Zone Automata** also makes an _Untimed_ Finite State Automaton given a *Timed Automaton* by combining states with a set of clock configurations to represent time.

```ad-tldr
*Zones* are a set of points in the =="clock space"== that are achieved by starting with the points that represent *clock configurations*, which can be reached when we get to a state from a transition, all possible clock configurations which can be reached by *elapsing time*
```

## Zones
A *Zone* is a set of clock valuations. We define $3$ operations of *zones* to help us model the configuration of clocks for a run in a *timed automata*.
- **Intersection** of two zones $W$ and $W'$ 
- **Resets** of a subset of clocks to $0$ in $W$
- **Future** of $W$: $\overrightarrow W=\{v+\delta\quad |\quad v\in W,\delta\in\mathbb{R}^{+}\}$  

using these three operations, we will emulate the change in a zone caused by a *transition*. Given a transition $t=\langle q, g, Y, q'\rangle$ we define
$$
\text{Post}_{t}(W) = 
\overrightarrow{
    [Y](W\cap\textlbrackdbl g\textrbrackdbl)
}
$$
where $[Y]$ denotes the resets and $\textlbrackdbl g\textrbrackdbl$ denotes the zone that is satisfied by $g$. 

## Zone Automata

Let $(q, Z)$ be a _symbolic state_ where $q$ is a state and $Z$ is a zone.
Let $s_{0}=(q_{0},\overrightarrow{\{\textbf0\}})$ be the initial state. Then the set of reachable symbolic states $\mathcal S$ is given by
$$
\frac{}{s_0\in\mathcal{S}}\text{Init}
$$
$$
\frac{\begin{matrix}(q,Z)\in \mathcal S && t=(q,g,Y,q') && Z'=\text{Post}_{t}(Z)\ne \emptyset\end{matrix}}{(q',Z')\in\mathcal S}\text{Trans}
$$
Whenever we derive a _symbolic state_ using the $\text{Trans}$ rule we also get a corresponding transition in the zone automata between the _symbolic states_.

But this method does not terminate. The two main approaches to that problem are [[Extrapolation for Zone Automata|extrapolation]] and [[Simulation for Zone Automata|simulation]].

[[Zone Automata Example]]

---
# References
