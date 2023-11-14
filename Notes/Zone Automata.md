---
tags:
  - Note
---
202310101410

Tags : [[Timed Automata]]

---
# Zone Automata
Consider this [[Train Track Crossing for Timed Automata|Example]]. It shows that having a Reachability Axiom is Important for software verification purposes. 

```ad-warning
title: Region Automata is Too Inefficient!
Lets say we have a Network of 10 Timed Automata, and each of these have 10 states. All of them have a single clock and the maximum number present guards of all of the automata is 2.

A naïve way would be to first construct a [[Monolithic Timed Automaton for a Network of Timed Automata|Monolithic Automata]] which accepts the same language.

The above construction gives $10^{10}$ states, with 10 clock and guards having the maximum number $2$.

The time bound that for Region automata construction would give time around $10!\cdot 2^{10}\cdot 10^{10}$. Doing a reachability check in this automata is not feasible. A better approach is required $!!$
```

Much like [[Region Automata]], **Zone Automata** also makes an _Untimed_ Finite State Automaton given a *Timed Automaton* by combining states with a set of clock configurations to represent time.

```ad-tldr
title: Tldr: Zones
*Zones* are sets in the **Clock Space**, which represent the set of clock configurations, these are obtained by
- Starting with a set of points
- Taking away the points that do not satisfy guards when the transition is taken
- Then adding points that can be achieved by waiting. i.e the *future* operator.
```

## Zones
A *Zone* is a set of clock valuations. We define $3$ operations of *zones* to help us model the configuration of clocks for a run in a *timed automaton*.
- **Intersection** of two zones $W$ and $W'$ 
- **Resets** of a subset of clocks to $0$ in $W$
- **Future** of $W$: $\overrightarrow W=\{v+\delta\; |\; v\in W,\delta\in\mathbb{R}^{+}\}$  

using these three operations, we will emulate the change in a zone caused by a *transition*. Given a transition $t=\langle q, g, Y, q'\rangle$ we define
$$
\text{Post}_{t}(W) = 
\overrightarrow{
    [Y](W\cap\textlbrackdbl g\textrbrackdbl)
}
$$
where $[Y]$ denotes the resets and $\textlbrackdbl g\textrbrackdbl$ denotes the zone that is satisfied by $g$. 
```ad-info
title:idea
$$
(q,Z)\xrightarrow{\text{guards}}(q, Z\cap\textlbrackdbl g\textrbrackdbl)\xrightarrow{\text{resets}} (q, [Y](Z\cap\textlbrackdbl g\textrbrackdbl))\xrightarrow{\text{elapse}}(q, \overrightarrow{[Y](Z\cap\textlbrackdbl g\textrbrackdbl)})
$$
```
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

Now we can start building our [[Reachability Algorithm for Zone Automata]]

But this method does not terminate. The two main approaches to that problem are [[Extrapolation for Zone Automata|extrapolation]] and [[Simulation for Zone Automata|simulation]].

[[Zone Automata Example]]

---
# References
[[Zone Automata Example]]
[[Extrapolation for Zone Automata]]
[[Simulation for Zone Automata]]
[[Reachability Algorithm for Zone Automata]]