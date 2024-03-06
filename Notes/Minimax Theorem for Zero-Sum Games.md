---
tags:
  - Example
---

202402221317

tags : [[Linear Programming]], [[Game Theory]]

#  Minimax Theorem for Zero-Sum Games
---
>[!Theorem]
>For every zero-sum game, worse case optimal strategies for both players exists and can be computed using [[Linear Programming]]. Moreover, if $\tilde{\mathbf{x}}$ is the worst case strategy for **Alice** and $\tilde{\mathbf{y}}$ is the worst case strategy for **Bob**, then the pair $(\tilde{\mathbf{x}},\tilde{\mathbf{y}})$ is a [[Mixed Nash Equilibrium]] and the number $\beta(\tilde{\mathbf{x}})=\tilde{\mathbf{x}}M\tilde{\mathbf{y}}=\alpha(\tilde{\mathbf{y}})$ is the same for all worst case optimal strategies.

Damn.

>[!check] Zero-Sum Games are ez
>This theorem, in a sense tells us everything about playing a zero-sum game, in particular "The worst-case optimal strategy is the best strategy".
>If **Alice** plays the worst-case optimal strategy then her expected payoff would always be at-least as much as the value of the game, no matter what strategy **Bob** plays. 
>If **Bob** is well informed and plays a worst-case optimal strategy, then they can ensure that **Alice** does not get more than the value of the game, no matter what strategy they choose.
>So there are no secrets involved and both players might as well declare their mixed strategies in advance and nothing changes.

>[!definition] What's in a Name
>If we consider the equality $\beta(\tilde{\mathbf{x}})=\alpha(\tilde{\mathbf{y}})$, and the worst case optimality of $\alpha$ and $\beta$ then we get the following.
>$$
>\max_{\mathbf{x}}\min_{\mathbf{y}}\mathbf{x}^TM\mathbf{y}=
>\min_{\mathbf{y}}\max_{\mathbf{x}}\mathbf{x}^TM\mathbf{y}
>$$

---
## Proof
First we show how an optimal strategy can be obtained using [[Linear Programming]] and then we prove the optimality condition. 

### Finding a Strategy for **Bob** for a given Strategy for **Alice**
That is, given an $\mathbf{x}$ we have to find the value of $\beta(\mathbf{x})$. Consider the following LP
$$
\begin{align}
&\text{Minimize}&&\mathbf{x}^TM\mathbf{y} \\
&\text{subject to}&&\left(\sum_{j=1}^ny_{j}\right)=1 \\
&&&\mathbf{y} \geq 0
\end{align}
$$
### Optimizing **Alice**'s strategy for the worst case scenario
Now that we can evaluate $\beta$, we just need to maximise $\beta(\mathbf{x})$.
This is unfortunately not a trivial LP as $\beta$ is not a linear function.  But we can use it using [[Primal - Dual LP|Duality of LP]].
Using the [[Primal - Dual LP|Dualization Recipe]] on the above LP, we get the following.
$$
\begin{align}
&\text{Maximize} &&x_{0}  \\
&\text{Subject to}&&M^T\mathbf{x}-\mathbf{1}x_{0}\geq \mathbf{0}
\end{align}
$$
This dual has just one variable as the original LP has just one equality constraint and all $x_i$ are still constants. By [[Primal - Dual LP|Duality Theorem]] we know that the optimal value for $x_0$ is $\beta(\mathbf x)$ 

Now to Maximize $\beta(\mathbf{x})$, we just convert all the constant $x_i$ to variable with appropriate conditions to have the following
$$
\begin{align}
&\text{Maximize}&&x_{0} \\
&\text{Subject to}&&M^T\mathbf{x}-\mathbf{1}x_{0}=\mathbf{0} \\
&&&\sum x_{i}=1 \\
&&&\mathbf{x}\geq0
\end{align}
$$
If the optimal solution to the above $LP$ is written as $(\tilde{x}_0, \tilde{\mathbf{x}})$ then along with the information that $\tilde x_{0}=\beta(\tilde {\mathbf{x}})=\max_{\mathbf{x}}\beta(\mathbf{x})$ 

### Finding Optimal Strategy for **Bob**
We follow basically the same steps are before to get the following LP which gives an optimal strategy for **Bob**.
$$
\begin{align}
&\text{Minimize}&&y_{0} \\
&\text{Subject to}&&M\mathbf{y}-\mathbf{1}y_{0}=\mathbf{0} \\
&&&\sum y_{j}=1 \\
&&&\mathbf{y}\geq \mathbf{0}
\end{align}
$$
Let the solution for this be $(\tilde{y}_{0},\tilde{\mathbf{y}})$

### The Solution is a Nash Equilibrium
>[!important] Punchline
>The brilliant thing about this solution is that the LP definition for optimal strategy for both **Alice** and **Bob** are *Duals*!

So by the [[Primal - Dual LP|Duality Theorem]] we get $\tilde{x}_{0}=\tilde{y}_{0}$ hence $\beta(\tilde{\mathbf{x}})=\alpha(\tilde{\mathbf{y}})$. And by the following [[Lemma for Minimax Theorem|lemma]] we also know that this is a [[Mixed Nash Equilibrium]].

---
# Related
- [[Mixed Strategies]]
- [[Mixed Nash Equilibrium]]