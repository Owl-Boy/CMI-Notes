---
tags:
  - Note
---
202410122010

Tags : [[Theory of Computation]]
# Formal Description of a 2-DFA
---
## Syntax
>[!definition]
>A 2-DFA is a 6-tuple defined as follows
>$$
>\mathfrak A = \langle Q,\Sigma \cup \{ \triangleleft, \triangleright \} ,q_{0}, q_{a},q_{r}, \delta \rangle
>$$
>where
>- $Q$ is the set of states
>- $\Sigma$ is the alphabet augmented with two special characters $\triangleright$ and $\triangleleft$, that act as start and end markers for the input.
>- $q_{0}\in Q$ is the start state
>- $q_{a}\in Q$ is the accept state
>- $q_{r}\in Q$ is the reject state
>- $\delta:Q\times \Sigma \to Q \times \{ L, R \}$

With the following restriction on the set of transitions.
- $\delta :(q, \triangleright) \mapsto (q', R)$
- $\delta :(q, \triangleleft) \mapsto (q', L)$
which just keeps us within the bounds of the word, along with
- $\delta: (q_{a}, -) \mapsto(q_{a}, -)$
- $\delta: (q_{r}, -) \mapsto(q_{r}, -)$
which states that we can never exit from the start or reject state.

---
## Semantics
A 2-DFA can be thought of as a finite tape with input written on it along with a control, which is a finite automata whose execution also describes the actions on the tape as shown in the figure.

![[2DFA.excalidraw]]

$q_{0}$ shows that initial location in the control. The input will be written on the tape and the tape head will be on the first letter after $\triangleright$.

For any given configuration (location of the head on the tape and the state in the automata), the transitions describe the next configuration of the automata.

![[Transition2DFA.excalidraw]]

---

## Accepting inputs

Given an input:
- If the control ever reaches the accept state, we stop the computation and accept the word (described in the syntax by not having outgoing transitions from accept and reject state).
- Similarly, if the control ever reaches a reject state, we stop the computation and reject the word.
- Unlike a simple DFA, a run in a 2-DFA can visit 2 configurations before reaching the accept state, in which case the machine gets stuck in a loop and we say that the input is rejected.

---
# References
[[2-Way DFA]]
[[2DFAs are equivalent to DFAs]]