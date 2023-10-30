202211141611

Type : #Note
Tags : [[Theory of Computation]]

---
# Turing Machines
### Informal Definition
A TM has a set of finite states and a semi-infinite tape whose left is marked with the $\vdash$ symbol, the input word, which is a finite word is written on the tap after the $\vdash$ symbol and the rest of the tape is filled with $\sqcup$, there is also a head(pointer), and we can read/write the cell it points to.
![[Pasted image 20221114164212.png]]
The Machine starts on a state $S$ and ends on the states $t$ if it accepts the word or ends at state $r$ if it rejects a word.

### Formal Definition
A Turing Machine is a 9-tuple
$$
M = (Q, \Sigma, \Gamma, \vdash, \sqcup, \delta, s, t, r)
$$
where 
- $Q$ is a finite set (the states).
- $\Sigma$ is a finite set (the input alphabet).
- $\Gamma$ is a finite set (tape alphabet) which contains $\Sigma$.
- $\vdash\in \Gamma-\Sigma$ , the left end marker.
- $\sqcup \in \Gamma - \Sigma$, the blank symbol.
- $\delta: Q\times \Gamma \to Q\times\Gamma\times\{L,R\}$, the transio
- $s\in Q$ (the start state).
- $t\in Q$ (the accepting state).
- $r\in Q, r\ne t$ (the reject state).
Intuitively the transition $\delta(q, \gamma) \to (p, \gamma', d)$ means, if at state $q$, the head reads $\gamma$ then replace $\gamma$ with $\gamma'$, moving the state $p$, and the head moves in the direction $d$(left or right).


The [[Turing Machine Configuration|configuration]] of the stack symbol is an element of $Q\times\{y\sqcup^\omega|y\in\Gamma^*\}\times \mathbb N$ which represent, the state, stack content and the position of the pointer.

![[Recursive and Recursively Eumberable Sets#Decidable an Semidecidable]]

There are several different flavours of turing machines and other machines that may seem more or less powerful but are computationally equivalent, some of them are, also known as **Turing Complete**: ^71be18
- [[Turing Machines with multiple tapes]]
- [[Two-Way Infinite Tape Turing Machine]]
- [[Two Stacks]]
- [[Counter Automata]]
- [[Enumeration Machine]]

Turing Macines can be simulated by other Turing machines, to do that we can construst can [[Universal Turing Machine]]. A Universal Turing machines is a turing machine whose language is 
$$
L(U) = \{M\#x\ |\ x\in L(M)\}
$$
Although Universal Turing Machines can simulate other Turing Machines, doing more advanced analysis on turing machines isn't easy, sometimes not even possible. 
[[Undecidability of the Halting Problem]] and [[Undecidability of the Membership Problem]] are some of the examples. ^71406d



---
# Related Problems

---
# References
[[Recursive and Recursively Eumberable Sets]]
