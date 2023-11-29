---
tags:
  - Note
  - Incomplete
---
202311201611

Tags : [[Advanced Algorithms]]
# Probabilistically Checkable Proof
---
$x:$ $n-$bit input
$y:$ certificate
$c:$ completeness
$s:$ soundness

Verifier $V$ uses $r(n)$ random bits, reads $q(n)$ bits of $y$.

If $x$ is a 'yes' instance, then for some $y$, $V$ accepts $x$ with probability $\geq c$.
If $x$ is a 'no' instance, then for any proof $y$, $V$ accepts $x$ with probability $\leq s<c$.

```ad-important
**PCP theorem:** $NP=PCP_{1, \frac{1}{2}}(O(\log n),k)$ for some constant $k$.
```

$PCP_{c,s}(r(n),q(n))$

*Hastad's PCP:* 
For any $\epsilon,\delta>0$, $NP=PCP_{1-\epsilon, \frac{1}{2}+\delta}(O(\log n),3)$.
Moreover, the verifier is restricted to use only the functions $odd(x,y,z)$ or $even(x,y,z)$.

**Input:** $x$, $|x|=n$ bits
Verifier picks a random string $r$, $|r|=c\log n$ bits
There are $n^{c}$ such possible strings.

If $x$ is a "yes" instance, V accepts $x$ with probability $\geq 1-\epsilon$, i.e. accepts on $\geq(1-\epsilon)n^{c}$ possible settings of $r$.
$\geq(1-\epsilon)n^{c}$ constraints in the CSP instance are satisfiable

If $x$ is a "no" instance, by PCP thm, V accepts $x$ with probability $\leq \frac{1}{2}+\delta$ on any $y$, i.e. $\leq\left( \frac{1}{2}+\delta \right)n^{c}$ constraints are simultaneously satisfiable.

--

Say we have an $\alpha-$approximation algorithm for MAX-CSP (number of constraints $=n^{c}$). If the instance is a "yes" instance, i.e. if $\geq(1-\epsilon)n^{c}$ are satisfiable, then our algorithm satisfies $\geq\alpha(1-\epsilon)n^{c}$ constraints.
If "no", then our algorithm satisfies $\leq\left( \frac{1}{2}+\delta \right)n^{c}$ constraints.

If $\alpha(1-\epsilon)m>\left( \frac{1}{2}+\delta \right)m$ then we can solve any problem in NP in polytime, $\implies P=NP$.

Consider $\epsilon,\delta\to_{0}$.

> [!check] Thus MAX-CSP (on odd/even constraints on 3 bits) has no approximation $> \frac{1}{2}$ unless $P=NP$.


## Reduction from Max-3CSP to Max-3SAT
---
For each of the even and odd functions, we construct four clauses each which have the following property: If the function evaluates to 1, all 4 clauses are satisfied, otherwise only 3 clauses are satisfied.


$$
odd(x_{i},x_{j},x_{k})\mapsto\left\{
\begin{align*}
(x_{1}\lor x_{j}\lor x_{k})\\
(\bar{x}_{1}\lor \bar{x}_{j}\lor x_{k})\\
(\bar{x}_{1}\lor x_{j}\lor \bar{x}_{k})\\
(x_{1}\lor \bar{x}_{j}\lor \bar{x}_{k})\\
\end{align*}
\right.
$$

$$
even(x_{i},x_{j},x_{k})\mapsto\left\{
\begin{align*}
(x_{1}\lor x_{j}\lor x_{k})\\
(x_{1}\lor x_{j}\lor x_{k})\\
(x_{1}\lor x_{j}\lor x_{k})\\
(x_{1}\lor x_{j}\lor x_{k})\\
\end{align*}
\right.
$$

So, a MAX-3CSP instance, $\psi$ with $m$ constraints $\mapsto$ a MAX-3SAT instance, $\phi$ with $4m$ clauses. If there exists an assignment that satisfies $k$ constraints, then it satisfies $4k+3(m-k)$ clauses.

$\psi$ is a yes instance $\implies \geq(1-\epsilon)m$ constraints are satisfiable
$\implies\geq 4(1-\epsilon)m+3\epsilon m=(4-\epsilon)m$ clauses of $\phi$ are satisfiable.

$\psi$ is a no instance $\implies\leq\left( \frac{1}{2}+\delta \right)m$ constraints are satisfiable
$\implies\leq 4\left( \frac{1}{2}+\delta \right)m+3\left( \frac{1}{2}-\delta \right)m=\left( \frac{7}{2}+\delta \right)m$ clauses of $\phi$ are satisfiable.

Unless $P=NP$, there is no $\alpha-$approximation for MAX-3SAT, where $\alpha$ satisfies $(4-\epsilon)m\alpha>\left( \frac{7}{2}+\delta \right)m$, or $\alpha> \dfrac{\frac{7}{2}+\delta}{4-\epsilon}\approx \frac{7}{8}+\frac{\delta}{4}$.

MAX-3SAT cannot be approximated to $> \frac{7}{8}$.

---
# References
[Williamson-Shmoys]