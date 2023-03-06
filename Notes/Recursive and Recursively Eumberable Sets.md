202211151011

Type : #Note
Tags : [[Theory of Computation]]

---
# Recursive and Recursively Eumberable Language
A Language is called recursively Enumerable if is accepted by a Turing Machine and Recursive if it is accepted by a Total Turing Machine.

recursive languages are closed under complementation but recursively enumerable languages are not.
This is because for Turing Machines which are not total, not accpeting and rejecting are not synonymous.
We can obtain a Total Turing machine which accpets the complement of a Recursive language by replacing the accepting and rejecting states.

If both the language and its complement is recursively enumerable then the language is _recursive_.
__Proof:__
Let $M$ and $M'$ be turing machines such that $L(M)=A$ and $L(M') =\ \sim A$. Build a Turing Machine $N$ which runs the input $x$ on both $M$ and $M'$ simultaneously on different tracks of its tape, hence $N$ contains alphabets of the form
![[Pasted image 20221115110918.png|400]]
where $a$ is the tape letter for $M$ and $c$ is the tape letter for $M'$
If the Machine $M$ ever accepts, then $N$ immediately accepts and if the machine $M'$ ever accetps then $N$ immediately rejects. Exactly one of the 2 cases must eventually occur as $x\in A$ or $x\in \sim A$ which are both recursively enumerable. Hence $L(N)$ is $A$ and $N$ is a total turing machine, Hence $A$ is recursive.

#### Decidable an Semidecidable
A property $P$ of a language is called _decidable_ if the set of all the strings having that property is recursive. Simlarly if all the strings having the property $P$ is called _semidecidable_ if the set of all the strings having the property is enumerably recursive. We can also say that if a set of strings has a semidecidable property, then there exits a turing machine which accepts them and loops or rejects on all other strings. 

---
# Related Problems

---
# References
[[Turing Machines]]