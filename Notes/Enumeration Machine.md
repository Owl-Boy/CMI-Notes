202211171911

Type : #Note
Tags : [[Theory of Computation]]

---
# Enumeration Machine
> [!info] Alan Turing and Enumeration Machies
> Turing machines were invented by Alan Turing. Originally they were presented in the form of enumeration machines, since Turing was interested in enumerating the decimal expansions of computable real numbers and values of real-valued functions. Turing also introduced the concept of nondeterminism in his original paper, although he did not develop the idea.
> 

An Enumeration Machine has a finite control and $2$ tapes, A read/write _work tape_ and a write-only _output tape_. The work tape head can move in either direction and can read and write any symbol from $\Gamma$ while the output tape can only move to the right and always writes one letter from $\Sigma$ before moving.

There is no input and no accepted or rejected state, the machine starts in its initial configuration with both the tapes empty. According to the transistion function it occasionally writes on the output tape, and when the control reaches an _enumerating state_, which is just a distinguished state. The word in the output tape is said to be _enumerated_. Then the output tape is cleared and its head is brought back to the start of the tape and the machines indefinitely continues from there.
$L(E)$ is the set of words ever enumerated by the enumeration machine $E$.

### Equivalence of Turing Machine and Enumerable Machines
A Turing Machine can simulate an Enumerable Machine using the following Procedure.

We let our turing Machine have 3 tapes, the first tape will contain the input.
The second and the third tape will be used to simulate the Enumerable machine, each time a new word is enumerated, it is checked to match with the input, and if it does then it is accpeted. All words that can be enumerated will be eventually accepted.

Similarly we can create an Enumerable Machine such $L(E) = L(M)$, but the following procedure does not work.
We can simulate the turing machine on the work tape for all $x$ that are accpeted by $M$, $E$ copies them to its output tape.

This does not work because the turing machine might not halt on some of the inputs hence the enumerable machine would get stuck forever.

The solution to this problem is _time sharing_. The work tape of the enumeration machine will be divided into multiple sections separated by $\#\in \Gamma$ on the turing machine will be simulated on all those sections. For each new input we can make a new simulation, for example we can make the turing machine simulate the first input in the first step, the first and second on the second step, and the first, second and third input on the third step, this way all words accpeted by the turing machine will eventually be accepted. 


---
# Related Problems

---
# References
[[Turing Machines]]