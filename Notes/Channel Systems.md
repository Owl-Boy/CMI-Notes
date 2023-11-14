---
tags:
  - Note
sticker:
---
202310241410

Tags : [[Theory of Computation]]

---
# Channel Systems
A **Channel System** is a [[Finite State Automaton|Finite State Automata]] which is similar to a [[Push Down Automata]] which uses a *Queue*(called *Channels*) instead of a *Stack*. **Channel Systems** are [[Turing Machines#^71be18|Turing Complete]] as reading and inputting the entire stack can be used to emulate a transition of a [[Turing Machines|Turing Machine]].

## Formal Definition
A **Channel System** $S$ is defined by the tuple $\langle Q, C,\Sigma, \Delta\rangle$ where
- $Q=\{q_{1}\dots q_{n}\}$ is a set of *control states*
- $q_{0}\in Q$ is an *initial state*
- $A$ is a finite set of *alphabet* and $\epsilon\in A$ 
- $C$ is a finite set of *channels*
- $\Delta:Q\times C\times\{?,!\}\times\Sigma^{*}\times A\times Q$ is a finite set of *transitions*

![[Pasted image 20231024145138.png]]

---
## Configuration
A **configuration** or a **global state** of a **channel system** with $n$ channels is an $n+1$ tuple $\in$ $Q\times \prod\limits_{i=1}^{n}(\Sigma^{*})$.
Intuitively, a configuration $(q, w_{1},w_{2}\dots w_{n})$ represents the current state and contents of each channel where $w_{i}$ represents the contents of the $i^{th}$ channel.

The initial configuration is $(q_{0},\epsilon,\epsilon\dots \epsilon)$.

---
## Execution
A transition $(q,c_{i},!,u,a,q')$ takes the control from state $q$ to $q'$ while writing $u$ to the channel $c_{i}$ after reading $a$.
A transition $(q, c_{i},?, u, a, q')$ takes the control from state $q$ to $q'$ while popping $u$ from the channel $c_{i}$ after reading $a$.
A transitions with $\epsilon$ neither writes, not removes from the channels.

A sequence of *Configurations* received by successive transitions is called a *Run*.

---
# References
[[Reachability in Lossy Channel Systems]]