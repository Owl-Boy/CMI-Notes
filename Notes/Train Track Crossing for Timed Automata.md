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



---
# Related
