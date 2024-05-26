---
tags:
  - Note
---
202405141005

Tags : [[Theory of Computation]]
# Time Petri Net
---
>[!hint] What and Why
>A *Time Petri Net* is used to model systems where process might happened in parallel and would still have time constraints. 
>They are like a [[Timed Automata]] and [[Petri Net]] hybrid where whenever a transition is enabled, the clocks for that transition start, and they are turned off when the transition is disabled. Triggering of the transition is depended on the clocks.

>[!definition] Time Petri Nets
>A *Time Petri Net (TPN)* is an a tuple 
>$$
>N = \langle P, T, F, SI, M_{0}, M_{F} \rangle
>$$
>
>Where
>- $P$ is the set of places 
>- $T$ is the set of transitions
>- $F \subseteq (P \times T) \cup (T \times P)$ is flow relation
>- $SI : T \to \mathbb{I}$ is the static interval function that takes a transition $t \mapsto (Eft(t), Lft(t))$ given the earliest and latest firing time for transition from when it is enabled.
>- $M_{0}$ and $M_{F}$ are the initial and final markings on the petri net.

## Semantics and Firing Condition
The Semantics of a *TPN* are given by a marking $M$ and a clock function $I : \text{Enabled}(M) \to R^+$. The clock function keeps track of the time that is spent before triggering transitions since it is enabled. 

The Initial configuration is given as $(M_{0}, \mathbf{0})$.

A transition after time $\theta$ from state $(M, I)$ to $(M'', I')$ are given by 
![[Pasted image 20240514134233.png]]

## Language of a Timed Petri Net
We can also add a labelling function $\lambda : T \to \Sigma$, this helps us construct a word from a sequence of transitions. Petri nets with a labelling function are also called Labelled Petri Nets (and similarly Labelled Timed Petri Nets).

Given a petri net $N$ with initial and final markings $M_{0}$ and $M_{F}$ we define the language of petri nets as 
$$
\mathcal L(N) = \{ (\lambda (t_{1}), \tau_{1}) \dots (\lambda( t_{n}), \tau_{n})\;|\; M_{0} [t_{1} \dots t_{}\rangle M_{f}, \tau_{i}-\tau_{i-1} \in SI(t_{i})\}
$$

---
# References
[[Petri Net]]
[[Timed Automata]]

