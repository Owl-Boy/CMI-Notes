---
tags:
  - Note
---
202401111401

Tags : [[Linear Programming]]
# Equational form of LP
---
The development of [[Simplex Method]] involves introducing two constraints to LP:
- All constraints are equations with non-negative right hand side (with the exception of the next type of constraint).
- All variables must be non-negative

>[!tip] Uses
>- *Equational Form* make algebraic manipulation eaiser (simplex method).
>- The general form makes it eaiser to think geometrically.
## Conversion to Equational Form
Every LP in general form can be converted to an LP in *equational form*.

### Removing Inequalities
We add dummy variables in the following manner
$$
6x_{1}+4x_{2}\leq 24 \quad\quad \to\quad\quad 6x_{1}+4x_{2}+s_{1} = 24, s_{1}\geq 0
$$
>[!idea]
>We let the extra slack allowed be the inequality be represented as a variable.

and the inequalities of the form 
$$
x_{1}+x_{2}\geq 800\quad\quad \to \quad\quad x_{1}+x_{2}-s_{2}=800,s_{2}\geq 0
$$
>[!idea]
>We let the extra variable represent the surplus allowed.

### Dealing with Unrestricted Variables
>[!idea]
>Any real number can be written as a difference of two positive real numbers.

Given and unrestricted variable $y$, we make the following changes 
$$
y = y_{1}-y_{2},\quad\quad y_{1},y_{2}\geq 0
$$
We replace every instance of $y$ with the above and add the variables $y_1$ and $y_2$.

## Every Equational Form LP can be thought of in General form
We can think of any equation of the form 
$$
ax_{1}+bx_{2}+\dots=c
$$
as 
$$
\begin{align}
ax_{1}+bx_{2}+\dots &\leq c \\
ax_{1}+bx_{2}+\dots &\geq c
\end{align}
$$

---
# References
[[Linear Programming]]
[[Simplex Method]]