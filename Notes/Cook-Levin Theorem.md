---
tags:
  - Note
  - Incomplete
---
202402121702

Tags : [[Complexity Theory]]
# Cook-Levin Theorem
---
> [!question] $SAT$ is $NP-$complete.

$SAT$ is a decision problem.
**Input:** Boolean formula $\varphi$
$SAT=\{ \varphi\ |\ \varphi \text{ is satisfiable.} \}$

[[NP (Complexity Class)|What is NP?]]

---
*Proof:*
$SAT\in NP$ because we can guess the satisfying assignment itself.

We want to show that any problem in $NP$ is polytime reducible to $SAT$.
Let $A\in NP$. For $x \in\Sigma^{*}$, we want
$M,x\mapsto \varphi_{x}$, where $\varphi_{x}$ is a boolean formula, s.t
$x \in A\iff \varphi_{x}\in SAT$.









---
# References
[Arora-Barak]