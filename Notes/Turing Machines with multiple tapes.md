202211171711

Type : #Note
Tags : [[Theory of Computation]]

---
# Turing Machines with multiple tapes
A Turing Machine with mutliple tapes intuitively hs 3 semi-infinte tapes and 3 heads which all point to different tapes and can move independently of each other. on each step, all 3 cells that the heads point to are read and then changed. It's transition functions would be of the type  $\delta: Q\times\Gamma^3 \to Q\times\Gamma^3\times\{L,R\}^3$  

A Turing Machine with 3 tapes can be simulated by a turing machine with a single tape.

The idea is that in the tape, each cell will store 3 letters in differnet "tracks" and on each track one symbol has a special mark to indicate where the head points to in each stack.
![[Pasted image 20221117175342.png|400]]
The tape symbols in $N$ belong to the set $\{\vdash\}\cup(\Gamma\cup\Gamma')^3$ 
where $\Gamma'\stackrel{\mathclap{def}}{=}\{\hat c|c\in \Gamma\}$ and
![[Pasted image 20221117180225.png|30]] is the blank symbol.
![[Pasted image 20221117180438.png|400]]

This is the initial configuration of the tape with the input copied on the first track

In each step the turing machine, we start from the left and move right till we read all the marked letters, the depending on the transition function of the multi tape turing machine we will change the tape, ad move the head back to the leftmost element for the next step.

Hence, a turing machine with multiple tapes is not more powerful than a regular turing machine.

---
# Related Problems
[[Two-Way Infinite Tape Turing Machine]]

---
# References
[[Turing Machines]]