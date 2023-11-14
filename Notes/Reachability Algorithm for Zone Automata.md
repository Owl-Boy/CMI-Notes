---
tags:
  - Note
---
202310190110

Tags : [[Timed Automata]]

---
# Reachability Algorithm for Zone Automata

This algorithm takes in a *Timed Automaton* as in put and check if the final states are reachable from the starting states.

It does this by Lazily generating _Symbolic States_ as it traverses the timed automata. Building a Zone Automata alongside it. The process if either the algorithm cannot traverse any further in the initial automata, or if new new Zones can be generated.

## The Naive Algorithm

We can use a subset relation between Zones to construct the following algorithm

![[Naive Algorithm for Reachability in Zone Automata#^a9400a]]

The correctness of the Algorithm is discussed in the note attached to the Image.

The problem with this algorithm is that it might not terminate on all inputs.

## Finite Abstraction of Zone Graph

The problem is that there needs to be a relation that does not let the automata produce an infinite sequence of zones that cannot be quotiented together into a finite set.

One way to do that is a [[Simulation for Zone Automata|simulation relation]].
The modified version of the naive algorithm that is correct and does terminate on all inputs, built using  a finite simulation relation instead of a subset relation is

![[Pasted image 20231019203056.png]]

It's correctness proof is almost identical to that of the [[Naive Algorithm for Reachability in Zone Automata|naive algorithm]] and the proof of termination is given in [[Simulation for Zone Automata]].

---
# References
[[Zone Automata]]
[[Naive Algorithm for Reachability in Zone Automata]]
[[Simulation for Zone Automata]]