---
tags:
  - Note
  - Incomplete
---
202310101010

Tags : [[Timed Automata]]

---
# Network of Timed Automata
We can have multiple timed automata running at the same time, that are synced with each other by accepting the common alphabet that they share, that is the syncing mechanism and both work independently if the letter don't match in multiple automata, (like b and c) for the class example.

If both the timed automata have a letter in common which is  going to be accepted, then the guards for both the automata need to be satisfied. This forces the syncing on clocks on common letter

A netwrok of timed automata is a bunch of processes, 
$\langle\mathcal A_{1},\dots,\mathcal A_{k}\rangle$
which have letters $\Sigma_{1}\dots\Sigma_{k}$ which need not be disjoints, but each of them have only a local set of clocks, i.e. $X_{i}\cap X_{j}=\emptyset$

If there are two automata have a letter in common, but they are in a configuration such that, the current states in the first one accepts the letter but the other one cannot accept it, in that the the letter is not accepted (if there a common letter in the alphabet, it MUST be accepted simultaneously, if it is not possible, then neither of the automata will continue evaluating)

We can Make a Synchronized Product (set product for states) to make a monolithic timed automata.
Doing the region automata nonsense for the monolithic thingy is absolutely infeasible. 

# "Better" Algorithm For Reachability



---
# References
