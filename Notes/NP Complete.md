202301051201

Type : #Note
Tags : [[Complexity Theory]]

# NP Complete
A problem is said to be **NP Hard** if $\forall A\in NP$
$$A\le_PL$$
If $L\in NP$ and $L$ is **NP Hard** then $L$ is called **NP Complete**

The **Cook-Levin Theorem** states that an **SAT** is **NP Complete**
_Proof_:
- **Idea**: Let $M$ be a nondeterminisitc turing machine with run time $n^k$ and $L=\mathbb L(M)$, we want to show that $L \le_P SAT$. To do this, we will show that for every language in **NP**, we can make a non deterministic turing machine such that it will take a polynomial time computational path, and for every corresponding path we can encode it in a boolean expression such that if the computational path is valid and is accepted then the boolean expression would be satisfied. 
- 

---
# Related Problems

---
# References
[[NP Complexity Class]]
[[Reduction]]