---
tags:
  - Note
---
202309231609

Tags : [[Timed Automata]]

---
# Event Clock Automata

```ad-caution
**Event Clock Automata** are not *Timed Automata* because of the use of [[Event Predicting Automata#Event Predicting Clocks|Event Predicting Clocks]].
```

Consider the language $\{aab\}\cup\{abb\}$ where the time gap between accepting the last two characters is $1$.

We can give an [[Event Recording Automata|Event Recording Automaton]] for the first word but not for the second word. And we can given an [[Event Predicting Automata|Event Recording Automaton]] for the second word but not the first one.

Hence both *Event Recording Automata* and *Event Recording Automaton* are not powerful enough, and neither of them are more powerful than the other. The [[Expressive Power Of Event Clock Automata]] is discussed here.

Now we create an *Event Clock Automaton* by combining the two.
We are allowed to use both *Event Recording Clocks* and *Event Predicting Clocks*
```ad-example
Let $L=\{a^{*}b^{*}\}$ such that:
- There exists an $a$ such that the first $b$ is accepted after time $1$
- There exists a $b$ such that it is accepted $1 unit$ after the last $a$

![[Drawing 2023-09-23 16.35.03.excalidraw]]

```

*Event Clock Automata* can also be determinized using the subset construction.
*Event Clock Languages* are closed under
- Union
- Intersection
- Complementation

---
# References
[[Event Predicting Automata]]
[[Event Recording Automata]]
[[Expressive Power Of Event Clock Automata]]