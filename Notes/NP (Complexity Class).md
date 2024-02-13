202301022001

Type : #Note
Tags : [[Complexity Theory]]

# NP (Complexity Class)
---
## NP
```ad-note
title:
Class of decision problems that can be *verified* in a [[Turing Machines|deterministic turing machine]] in polynomial time, or the the problems that can be decided by a non deterministic turing machine in polynomial time.
```

$\Sigma=\{ 0,1 \}$ is our alphabet.
$A\subseteq\Sigma^{*}$ is in $NP$ if there exists a binary predicate $R(x,y)$ s.t. $x,y\in\Sigma^{*}$ and $R$ is in $P$, and there is a polynomial $p(n)$ s.t. $\forall x \in\Sigma^{*}$, $x \in A \iff \exists y \in\Sigma^{p(|x|)}$ s.t. $R(x,y)=1$.

### Examples

- **NP-machine** - The language accepted by the NP machine is an NP-complete problem.
- **SAT** - Given a boolean expressions is there an assignment of variables such that the expression evaluates to True? Here $x$ would be the boolean formula, and $y$ the assignment of values.
- **3-COLOUR** - Given a graph, is there a way to colour the vertices using three colours such that no two neighbouring vertices have the same colour?
- **HAMILTONIAN** - Given a graph, does it contain a Hamiltonian path?

If **P $\ne$ NP**, then there are infinitely many complexity classes between **P** and [[NP Complete]]. Problems like Factoring and Graph Isomorphism are problems which are thought to be neither **NP Complete** nor **P**.

---
# References
[[Complexity Classes]]