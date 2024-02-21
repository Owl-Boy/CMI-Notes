---
tags:
  - Note
  - Incomplete
---
202402141102

Tags : [[Complexity Theory]]
# Complete problem for NL
---
$PATH=\{ (G,s,t):G\text{ is a digraph, there exists an }s \text{ to }t\text{ directed path} \}$

This problem is complete wrt *logspace many-one reductions*.
$f:\Sigma^{*}\to\Sigma^{*}$ is logspace computable if we have the input tape as read-only, $n-$length, have logspace for computation, and have the output tape as write-only, one-way, $n-$length so that we can't use it as workspace.

We also want transitivity. $A\leq_{m}^{L}B\leq_{m}^{L}C$.
We have $x\mapsto f(x)\mapsto g(f(x))$. But we can't calculate $f(x)$ and store it, and use it to calculate $g(f(x))$. But we can calculate bits of $f$ lazily, when $g$ requires it.

---
# References
