---
tags:
  - Note
---
202409262109

Tags : [[Concurrent Programming]]
# Consensus Number of Atomic Read Write Registers
---
Here are some ideas that will be used repeatedly for finding the consensus number of atomic read-write registers

1. A *run-tree* is a tree where each node denotes the state of the system and each child corresponds to the new state after one thread executes 1 step, for convenience we assume that there are up to $M$ children of each node if there are $M$ threads and the $i^\text{th}$ child represents a step in the $i^\text{th}$ thread.
	- The leaves of the tree correspond to termination of all programs
	- Since the algorithm is wait-free, the three must have finite depth.
1. A *valency* of a node $n$ is the number of values that leaves of the sub-tree rooted at $n$ can take.
	- If all leaves agree then the node is said to be *univalent*
1. If all the variables are given the same input, then consensus is trivial, other wise, there must be at least $1$ *multi-valent* node
	- Consider the case where one thread has input $0$ and another thread has input $1$, then if we take the left most child, that represents the execution path where the first thread reached a consensus on its own and the right most path represents the execution where the other thread reached consensus on its own. This forces the root node to be *multi-valent*.
1. We say that a node is *critical* if it is *multi-valent* and all its children are *univalent*.

---

>[!error] Claim
>There is no wait-free boolean consensus algorithm for that uses only atomic variables for boolean domain for two threads.

The proof is just a case bash when we start at a critical node and show that both children can end up at the same value.

- Next operations on each thread commute.
	- In that case we consider the runs that start with $\text{OP}_{1} \triangleright \text{OP}_2$ and $\text{OP}_{2}\triangleright \text{OP}_{1}$. 
	- $\text{OP}_{1}$ and $\text{OP}_{2}$ go to different branches from the critical node hence lead to univalent nodes of differnt value, but their compositions get to the same configurations hence enabling a run from both branches that end up with the same consensus.
- One of the operations is read, and the other one is write
	- Without loss of generality, say $\text{OP}_{1}$ is a read and $\text{OP}_{2}$ is a write.
		- Then $\langle p, q, M\rangle \xrightarrow{\text{OP}_{1}}\langle p', q, M\rangle\xrightarrow{\text{OP}_{2}}\langle p', q', M'\rangle$ 
		- And $\langle p, q, M\rangle\xrightarrow{\text{OP}_{2}}\langle p, q', M'\rangle$
	- From both the threads we start runs that always take right paths that ignore the first thread. Both will end up with the same decisions, which is a contradiction.
- Both operations are write
	- Exact same proof as above.

---
# References
[[Consensus Number of Atomic Read Write Registers and Atomic Queue - 2]]