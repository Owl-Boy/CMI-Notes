---
tags:
  - Note
  - Incomplete
---
202311041311

Tags : [[Timed Automata]]
# Expressability of One-Clock Alternating Timed Automata
---
Consider the following languages:
$$
L_{1}\quad:=\quad\{(a^n,\tau)\;:\;\not\exists i<j \text{ such that }\tau _{j}-\tau_{i}=1 \}
$$
This language cannot be accepted by a *Timed Automata*, but it can be accepted by the following [[Alternating Timed Automata]]
![[1-clock TImed Automata Example.excalidraw|600]]

Next, consider the following language.
$$
L_{2}\quad:=\quad\{(a^k,\tau)\;:\; (\tau_{1}<\tau_{2}<1)\land(\tau_{1}+1<\tau_{k}<\tau_{2}+1\text{ for exactly 1 }k)\}
$$
This cannot be accepted by a *1-clock ATA* but the following *Timed Automata* accepts it
![[Finite Automata example.excalidraw|600]]
[[Proof that L2 cannot be accepted by a 1 Clock Timed Automata|Proof]] that $L_2$ cannot be accepted by a *1-clock ATA* is fairly non-trivial

Hence The expressive power for *1-clock ATA* and *Timed Automata* comparable.

---
# References
- [[Proof that L2 cannot be accepted by a 1 Clock Timed Automata]]
- [[Alternating Timed Automata]]
- [[Alternating Finite Automaton]]
