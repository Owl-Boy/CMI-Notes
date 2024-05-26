---
tags:
  - Note
aliases:
  - Kripke Structures
---
202309111109

Tags : [[Logic]]

---
# Kripke Models

A *Kripke Model* is a triple of the form:
$$
\mathcal C = \langle 
                  C
                , \le
                , \Vdash 
             \rangle
$$
Here:
- $C$ is a non-empty set, whose elements are called *states* or *possibilities worlds*.
- $\le$ is a quasi order on $C$ which represent the "Timeline".
	- Sometimes a $R \subseteq C \times C$ successor relation is used instead of a quasi order.
- $\Vdash$ is a binary relation between elements of $C$ and propositions which represents "The knowledge we know at that point in the timeline". AKA the labelling function.

---
## Example
### Mod 2
Program : `x := x + y mod 2`

![[mod-2-kripke.excalidraw|500]]

### Concurrency
Program:
```
Prog1:
1   while True
2       wait (turn = 0)
3       turn := 1

Prog2:
1   while True
2   	wait (turn = 1)
3   	turn := 0
```
![[Concurrency Kripke.excalidraw]]

---
# References
[[Linear Temporal Logic]]
[[Intuitionistic Logic]]
[[Some Applications of Kripke Structures]]