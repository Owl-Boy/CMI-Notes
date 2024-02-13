---
tags:
  - Note
  - Incomplete
---
202401271401

Tags : [[Linear Programming]]
# Simplex Method
---
>[!idea] An Algorithm for Solving Linear Programming
>The LP should be in [[Equational form of LP|equational form]].
>- We start with a [[Basic Feasible Solution|bfs]].
>- Deduce whether it is optimum or if LP unbounded
>- If not, we move to another *bfs* with higher cost

>[!example] Example for demonstration
>Maximize $x_{1}$ subject to the constraints
>$$
>\begin{matrix}
> x_{1}  & - &  x_{2} &  \leq &  1 \\
> -x_{1} & + & x_{2}  &  \leq & 2 \\
>x_{1} & , & x_{2} & \geq & 0
>\end{matrix}
>$$ 

## Step 1: Convert to equational form
Converting the above linear program to the following form
$$
\begin{matrix}
x_{1} & - & x_{2} & + & x_{3} &  & &  = & 1 \\
-x_{1} & +& x_{2} &  & &  + & x_{4}& = & 3 \\
x_{1} & , & x_{2} & , & x_{3} & , & x_{4} & \geq & 0
\end{matrix}
$$
The representing matrix looks like
$$
A=
\begin{bmatrix}
1 & -1 & 1 & 0 \\
-1 & 1 & 0 & 1  \\
\end{bmatrix}
$$
---

>[!todo] Step 2: Finding a Basic Feasible solution and tableu form

 Pivot for now:
$$
\frac{
\begin{matrix}
x_{3}  &  =  & 1  & - & x_{1} & + & x_{2}  \\
x_{4} & = & 2 & + & x_{1} & - & x_{2}
\end{matrix}
}{
\begin{matrix}
z & = & &  & &x_{1} & &   &
\end{matrix}
}
$$



---
## Step 3: Pivoting
At a tableau $T$, if we look at costs:
- If all the variables in the cost row have negative coefficients, then we have the optimal solution the LP
- If there is a variable in each row that is positive, say $x_1$
	- If all coefficients of $x_i$ are non-negative, then the LP is unbounded
	- Otherwise we pivor at $x_2$

Looking at the bottom row of the tableau. we see that $z$ will increase if we increase $x_1$, an from other rows, we see that $x_1\in [-2,1]$, so we set make $x_{1}$ now one of components for the bfs and get the following tableau
$$
\frac{
\begin{matrix}
x_{1}  &  =  & 1  & - & x_{3} & + & x_{2}  \\
x_{4} & = & 3 & - & x_{3} &  & 
\end{matrix}
}{
\begin{matrix}
z & = & 1& - & x_{3}& + & x_{2}
\end{matrix}
}
$$

Now we can only pivot from 2, but there is no upper bound to the value of 2, so we conclude that the LP is unbounded.

Out Basic feasible solution therefore is $\langle1,0,0,3\rangle$ and we can add any multiple of $\langle 1,1,0,0\rangle$ to it.

---
## Example for it working
![[Pasted image 20240127163149.png]]

---
# References
