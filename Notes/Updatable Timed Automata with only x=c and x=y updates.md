---
tags:
  - Example
---

202310301124

tags : [[Timed Automata]]

#  Updatable Timed Automata with only $x:=c$ and $x:=y$ updates
---
>[!note] Theorem
>*Updatable Timed Automata* where the only updates allowed are $x:=c$ and $x:=y$ are just as expressive as regular *Timed Automata*

To prove the above theorem we will give a construction from the given subset of [[Updatable Timed Automata]] to [[Timed Automata with Diagonal Constraints|D-Timed Automata]].

---
## Converting to D-Timed Automata
### Dealing with $x:=c$ 
For this step, make copies of our automata for all of the $c$ that are used to update a given clock.

Now for every transition that has the clock $x:=c$, we change it such that the transition resets $x$ and takes it to the copy of the automata for $c$. In every guard of every transition of that automata $x$ is replaced with $x-c$.

We do that for every single clock and now we have eliminated all resets of the form $x:=c$.

### Dealing with $x:=y$
For a pair of clocks $x, y$ we first make a copy of the automata and replace all $x$ with $y$ any transition which contains the update $x:=y$ will be taken to that copy of the automata.
Now resetting $x$ to a constant will take us back to the original automata, but resetting $y$ is a problem.
So we make another copy of the automata, and swap all $x$s and $y$s in the guards. Whenever we are in the $x:=y$ automata and we see a reset of $y$ we instead reset $x$ and go the new automata we created.

Thus we have eliminated both kinds of updates and we have that the [[Updatable Timed Automata]] with just $x:=c$ and $x:=y$ is not more expressive than a regular timed automata.

---
# Related
[[Updatable Timed Automata]]