---
tags:
  - Note
  - Incomplete
---
202409131809

Tags : [[Software Verification and Analysis]]
# IC3 Algrorithm
---
>[!check] Idea
>The goal is to verify temporal properties on systems and in the book [Temporal Verification of Reactive Systems](https://link.springer.com/book/10.1007/978-1-4612-4222-2), the authors discuss 2 strategies for strengthening invariant properties
>- Using stronger assertions
>- Conduct an incremental proof using previously established invariants

>[!example]
>Consider the system: 
>```python
>x, y := 1, 1
>while *:
>	x, y := x + 1, x + y
>```
>And we want to prove that $P := y >= 1$ is an invariant.
>This statement is true on line 1, but it does not hold with $y = x + y$
>Hence we need to strengthen $P$ to make it an inductive invariant.
>Here it is clear to see that a stronger statement that is also inductive is 
>$$
>x \geq 0 \land y \geq 1
>$$
>This inductive invariant could have given from the beginning but for people it is almost always easier to come up with an inductive invariant.

***IC3*** is a result of asking: If incremental methods is often better for humans, might it be better for algorithms as well?

A direct enumerative approach is possible, but it is very computationally intensive and hence a more property directed approach seems useful. One straightforward way to implement is to guide the search for inductive instances with counter-examples(CTI).

For example, if the equation
$$
y \geq 1 \land x' = x + 1 \land y' = y+x \not\Rightarrow y \geq 1
$$
is given to an SMT solver, it will return $x = -1 \land y = 1$. Until this state is eliminated, the property $P$ cannot be proven.

The constraints are of the form $ax+by+c \geq 0$ augmented with $a(-1) + b(1) + c< 0$. There is a chance that the resulting constraint is inductive, for example $x \ge 0$.

---
## The Algorithm
Consider a finite state system $S: (\bar{i}, \bar{x},I(\bar{x}), T(\bar{x},\bar{i}, \bar{x}'))$, where $I(\bar{x})$ is the initial configuration and $T$ is the transition relation.

Let $P$ be an assertion. The first check is if $P$ is inductive with 2 sat queries
$$
\begin{matrix}
I \implies P & \text{and} & P \land T \implies P'
\end{matrix}
$$
If they hold, $P$ is an invariant. If the first query fails, $P$ is falsified. If the induction fails, then there is a state that can lead to error in one step, so $s$ is a CTI.

The inductive clause generator tries to find a clause that is inductive and it falsifies $s$ and then

$$
\phi_{1} \land P \land T \implies P'
$$

If the induction proof still fails, then a new clause is generated which now has to be inductive relative to $\phi_{1}$ and more generally its predecessors, so the final clause becomes
$$
P \land T \bigwedge \phi_{i} \implies P'
$$
If there are no such $\phi_i$ then  
 

# References
[Understanding IC3](https://dl.acm.org/doi/10.1007/978-3-642-31612-8_1)
[Temporal Verification of Reactive Systems](https://link.springer.com/book/10.1007/978-1-4612-4222-2)