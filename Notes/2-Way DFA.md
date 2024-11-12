---
tags:
  - Note
---
202410122010

Tags : [[Theory of Computation]]
# 2-Way Determinisitic Finite State Automata
---
>[!idea] What
>A [[Deterministic Finite State Automata|DFA]] can be thought of as a computation model that receives input on a tape that it can read one letter at a time as its attention (tape head) moves one letter to the right every time. After reading the entire input 
>
>The restriction of the machine to only be allowed to move its tape head from left to write also gives *DFAs* the name '1-way DFA'. 
>If we remove that restriction and allow our tape head to move in both directions, we get what is called a 2-way deterministic finite state automata (or 2-DFA).

This means that a *2-way deterministic finite state automata* is a model of computation that is similar to a simple DFA, but has the ability to go back and re-read sections of the input word.

>[!note]
>A 2-DFA is equivalent to a read-only turing machine with finite tape.

For a formal description, check [[Formal Description of a 2-DFA]].

[[2DFAs are equivalent to DFAs]] (very unfortunate imo, but also based) but they have 2 advantages over regular DFAs
1. Consider the language $(a+b)^*a(a+b)^{n-1}$, which is the language of all words that have $a$ as their $n^\text{th}$ last letter.
	- A DFA for for the above language will require $2^n$ states
	- For a 2DFA, we can stay in the start state till we reach the end marker and then use $n$ states to move $n$ steps back and go the accept state if we read an $a$ and reject state if we read a $b$. 
	- The above construction shows that 2DFAs provide exponential succinctness.
2. 2DFA is semantically very close to a constant memory program, where one is usually allowed to re-read parts of the inputs, hence for a lot of problems, these might be easier to reason with,

---
# References
[[Formal Description of a 2-DFA]]
[[2DFAs are equivalent to DFAs]]