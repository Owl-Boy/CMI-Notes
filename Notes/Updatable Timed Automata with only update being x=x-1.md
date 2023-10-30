---
tags:
  - Example
---
202310301110

Tags :[[Timed Automata]]
# Updatable Timed Automata with only update being $x:=x-1$
---

>[!note] Theorem
>[[Updatable Timed Automata]] with the only update being $x:=x-1$ is more expressive than a regular timed automata

To prove the theorem we simulate a 2-[[Counter Automata]] using the given subclass of UTA.

---
## Simulation of a 2-Counter Automata

The process of simulate a 2-Counter Automata is almost identical to the process for doing this in the general case discussed [[Emptiness for Updatable Timed Automata|here]]. With the only problem being increments.

We redo the increments in the following way.
Given the transition
$$
q\xrightarrow[c_1++]{a} q'
$$
we create the following transition on the UTA
$$
q\xrightarrow[x_{2}:= x_{2}-1]{a,\quad x_{\text{fix}}=1,x_{\text{fix}}:=0}
$$
Idea being, we let the time elapse exactly 1 second, and reset all the clocks that are not implemented.

---
# References
[[Updatable Timed Automata]]
[[Emptiness for Updatable Timed Automata]]