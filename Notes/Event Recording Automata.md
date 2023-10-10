202309071109

Type : #Note 
Tags : [[Timed Automata]]

---
# Event Recording Automata
An *Event Recording Automata* is a timed automata, such that we have a clock for each letter in the alphabet and those are the only clock $\{X_{a},X_{b}\dots X_{n}\}$, and a clock is reset iff the letter corresponding to the clock is read.

```ad-info
title: Motivation: Subset Construction

Resetting of clocks which go out of sync created a problem while subset construction. 

Consider A Non-deterministic Timed Automata. And we attempt to determinize it by the subset construction.

![[Drawing 2023-09-07 12.14.54.excalidraw|200]]

So consider the above situation.
We can perform the subset construction to get this situation which workds

![[Drawing 2023-09-07 12.18.33.excalidraw|200]]

But the problem arises when we reset clocks

![[Drawing 2023-09-07 12.22.03.excalidraw|200]]

If we try to do the same thing, we encounter the following issue.

![[Drawing 2023-09-07 12.25.19.excalidraw|200]]

Here reseting or not reseting the clock messes up guards and timings of atleast of the component timed automata 
```

An example of a language accepted by ERA would be $\{(ab*a)\ :\ \text{distance between the }\text 2\ a's\text{ is } 1\}$
An example of a language which cannot be accepted by an ERA would be
$\{(aaa) : \text{distance between last } 2\ a's \text{ is } 1\}$

*Event Recording Languages* are closed under 
- Intersection
- Union
- Complementation

And all *Event Recording Automata* are determinizable by the subset construction

---
# References
[[Deterministic Timed Automata]]
[[Event Predicting Automata]]
[[Event Clock Automata]]