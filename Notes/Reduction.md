202301051201

Type : #Note
Tags : [[Theory of Computation]]

---
# Reduction
$f:\Sigma^*\to\Sigma^*$ is a polynomial time computable function.

$$A\le_P B$$
is a polynomial time reduction if there exits a polynomial computable function $f:\Sigma^*\to\Sigma^*$ such that
$$x\in A\iff f(x)\in B$$
A **Reduction** from $A$ to $B$ can be intuitively thought as.
	$A$ is not any harder than $B$
Since a subroutine in $B$ can  be used to solve $A$  

If $L_1$ and $L_2$ are both reducible to each other 
$$
\begin{equation}
\left.
\begin{matrix}
L_1\le_P L_2\\
L_2 \le_P L_1
\end{matrix}
\right\}\iff L_1 \equiv_P L_2
\end{equation}
$$

---
# Related Problems

---
# References
