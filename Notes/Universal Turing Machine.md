202211171911

Type : #Note
Tags : [[Theory of Computation]]

---
# Universal Turing Machine
A Universal Turing machine $U$ is a turing machine whose language us 
$$
L(U) = \{M\#x\ |\ x\in L(M)\}
$$
The first step is to encode $M$ as an input along with $x$ for example
$$
0^n10^m10^k10^s10^t10^r10^u10^v1
$$
This might represent that the machine has $n$ states represeted by the numbers $0$ to $n-1$, 
It has $m$ tape symbols represented by the numbers $0$ to $m-1$,
of which the first $k$ are input symbols,
$s$ is the starting state while $t$ and $r$ are accpeting and rejecting states,
$u$ is the left marker and $v$ is the blank.

The remainder of the string can consist of transitions of the form 
$$
0^p10^a10^q10^b10 \to ((p, a), (q, b, L))
$$
Once we have such an encoding we can proceed to build a universal turing machine

We can have The description of the machine one the first tape, the input on the second tape and the information about the state the machine is in and where the header is located in the third one.
On each step of $M$ it reads the data in the third tape and the letter that the head is pointing to, and after reading the transition from the first tape it updates the other $2$, as soon as the $M$ accepts of rejects a word, so does $U$

If the number of letters used in $M$ are more than that in $U$, then each letter has to be encoded using letters of $U$.

---
# Related Problems

---
# References
[[Turing Machines]]