202211171811

Type : #Note
Tags : [[Theory of Computation]]

---
# Counter Automata
A $k$-counter Automata is a machine equipped with a two-way read-only input head and $k$ integer counters that can store an arbitrary non-negative integer. In each step we can independently increment or decrement one cell in either direction, test them for $0$ or move the head by one cell in either direction.

### Using 2 counters to simulate a stack
A counter Automata with $2$ counters can simulate a stack. The stack symbols can be written in binary and the numbers can be concatenated to form a huge binary strings which will be the number represented in the stack.

After each step of the stack, one the counter will hold the contents of the stack and the other one will be kept empty so that the contents will be transferred to it in the next step.

To simulate pushing a zero, we reduce the non empty stack by one and adding 2 to the empty one repeatedly till the first one reaches zero, to simulate adding a 1, its the same procedure but we increment a 1 in the end, to simluate popping we can decrement one of the counters and add one to the other counter every other turn, the parity of the decrement will tell if it popped a 1 or a 0

Since a two- stack machine can simulate an arbitrary turing machine we can say that a 4-counter automata can simulate a turing machine.
But we can do better 

### Simulating a turing machine with 2-counter automata
A Turing machine can be simulated by a 4-counter automata, if the values in the 4 counters are represented by $i,j,k,l$ then the two counter automata can have the value $2^i3^j5^k7^l$ 
adding 1 one to the third counter can be simulated by multiplying the counter by $5$, hence a 4 counter automata can be simluate by a 2 counter automata,

Thus a turing machine can be simulated by a 2-counter automata. Even though it would be ridiculously inefficient and even simulating one step of a turing machine will take a lot of steps

One counter automata are not as powerful as a turing macine but they can accept non-CFLs like $\{a^nb^nc^n | n>0\}$ 

---
# Related Problems
[[Two Stacks]]

---
# References
[[Turing Machines]]