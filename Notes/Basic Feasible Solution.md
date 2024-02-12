---
tags:
  - Note
---
202401111701

Tags : [[Linear Programming]]

---
# Basic Feasible Solution

>[!tip] Intuition
>- Around the "Interior" points of feasible region, we can make a tiny line segment passing through the point, that is entirely in the region, this cannot be done with "vertices"
>- ![[Pasted image 20240111161448.png]]
>- So if the constraints are given in the form of $Av=b$ where $v$ is a *feasible point*, we find a $w$ such that $Aw=0$ so $A(v+\lambda w)$ would also be feasible for some $\lambda$ is some tiny set $(\alpha, -\alpha)$.
 
One way to formalise the notion of "moving along a line segment" would be finding a *feasible point* $v$ such that $A v=b$. Now consider $v_{i_1}A^{i_{1}}+\dots+v_{i_{k}}A^{i_{k}}=b$ with just the non zero columns of $A$.

If the columns are linear dependent then we can find $\alpha_1 \dots \alpha_k$ such that $\alpha_1 A^{i_1}+\dots\alpha_{k}A^{i_{k}}=0$ and we let $w$ be the vector with corresponding components $\alpha_i$. So we have $A w=0$. Also we can find a $\lambda$ such that $v\pm u\ge{0}$. This is the line we can move along inside the region.

On the other hand, If the non-zero columns are linear independent, we cannot find such a $w$. We cannot move around such points in a line, they are like our *vertices*.

>[!definition] Basic Feasible Solution
>A *Basic Feasible Solution* of an LP maximises $c^Tx$ subject to $Ax=b, x\geq 0$ is a feasible solution If there exists an $m$ element set $B\subseteq\{1\dots n\}$ such that 
>- The columns indexed by $B$ are linearly independent.
>- Components of $x$ not indexed by $B$ are $0$.
>
>Alternatively A *feasible point* is a *basic feasible solution* if the set of columns indexed by $K=\{i\;|\;v_i > 0\}$ are linearly independent.
>
>Both Definitions are equivalent. Trivial.



## Example: 
1. 
$$
\begin{matrix}
2x_{1} & + & x_{2} & + & 4x_{3}  & & & = &8 \\
 &  & x_{2} &  &  & + & x_{4} & =&4 \\
x_{1} & , & x_{2} & , & x_{3} & , & x_{4} & \geq&0
\end{matrix} \\ \\
$$

Here $B=\{1,2\}$ and we can find $v= (2, 4)$ as a *basic feasible solution*

2. 
   $$
   \begin{align}
x_{1} +x_{2}+x_{3}=1\\
x_{1},x_{2},x_{3}\geq 0
\end{align}
$$
In this case $B=\{1\}$, so  $(1,0,0)$ is an fbs, but $(0.4, 0.6, 0)$ is not a feasible solution.
---
# References
[[Solution of an LP]]
[[Simplex Method]]
[[Optimality of Basic Feasible Solution]]