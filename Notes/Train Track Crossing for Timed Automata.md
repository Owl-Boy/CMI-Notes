---
tags:
  - Example
---

202310101458

tags : [[Timed Automata]]

# Train Track Crossing for Timed Automata
---
```ad-question
There is a *Road* and *Train Tracks* that cut through it.
On either side of the *Train Tracks* there are gates which close when a train is passing to prevent vehicles and pedestrians from trying to cross at the same time.

Design a system to automate the functioning of the gates.
```

A possible system to model the above situation can be to construct a [[Networks of Timed Automata]] where we have a *Timed Automaton* for each of the following.
- The Train
- The Gate
- The Controller which is there to help the gate and the train communicate.

![[Railway Crossing Timed Automata.excalidraw|1000]]

In the above model, we see that whenever the train approaches in the left automata, it also triggers the transition in the middle one, for the controller, which then signals the gates to close within 2 seconds. 
Similarly when the train is leaving, the controller triggers the opening of the gates after a certain time interval.

The starting state of the system is $\langle \text{Far}, \text{waiting for train}, \text{open}\rangle$

```ad-hint
title: Motivation for reachability algorithms
Here it is important to notice that even though the state space has $4^{3}=64$ states, there are certain states that should not be reachable, like the state
$\langle\text{near}, -, \text{open}\rangle$.
Hence it is important to have reachability algorithms for model checking.
```

---
# Related
[[Zone Automata]]