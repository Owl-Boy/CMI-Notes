202308181008

Type : #Note
Tags : [[Algebraic Graph Theory]]

---
# Block
Let $(\Gamma,X)$ be a _Transitive Permutation Group_. A block $B$ is a subset of $X$ such that $\forall \sigma \in\Gamma,\sigma(B)=B$ or $\sigma(B)\cap B=\emptyset$.
- **Trivial Block**: $B=\emptyset, B=X, B$ is a singleton
- **Non Trivial Block:**
	- $\Gamma =\mathbb Z_{n}$ in its action on $X=[n-1]$, $\Gamma=\langle\sigma\rangle$ where $\sigma(i)=i+1\mod n$ 
	- Let $n=10$ then $\{0,5\}$ and $\{0,2,4,6,8\}$ are blocks.

If $B$ is a block and let $B'=\sigma(B),\sigma\in\Gamma$ then $B'$ is also a block.
And The transitivity property ensure that given a block, all the other blocks  that can be derived from it, have the same size and form a partition of $X$.

---
# References
[[Primitive Transitive Permutation Group]]