202211172111

Type : #Note
Tags : [[Theory of Computation]]

---
# Undecidability of the Halting Problem
We can encode a turing machine and simulate it on another turing machine, but doing further analysis on a turing machine is not always possible, for example, there is no turing machine, that would take in a turing machine and an input for the turing machine as its inputs and return if the machine will halt on it input.

Assuming the accepting language of all turing machines is $\{0,1\}$

The constructions uses the [[Diagonalization|diagonalization]] argument.
let $HP$ be the set of all turing machines, and there is a turing machine $H$ that takes in inputs of the form $M\#x$ that accepts if $M$ halts on $x$ and rejects otherwise. Therefore $H$ is a total turing machine.
we can label the turing macine by $\Sigma^*$, so we have $M_\epsilon,M_0,M_1,M_{00},M_{01}\dots$
and we can make a matrix
![[Pasted image 20221118001530.png]]
here the i,jth elment is $L$ if $M_i$ halts on $j$

Now we make a make a Turing Machine $N$ that takes $x$ as its input and it halts if $M_x$ loops on $x$ and it loops of $M_x$ halts on $x$., Hence, $N$ differs from every single $M_x$ for atleast some input

This is a contradiction as $HP$ is supposed to be the set of all Turing Machines, which includes $N$, but $N$ cannot differ from itself at any point.

---
# Related Problems
[[Undecidability of the Membership Problem]]

---
# References
[[Turing Machines]]