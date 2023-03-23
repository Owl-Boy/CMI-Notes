202303121003

Type : #Note
Tags : [[Differential Equations]]

---
# Linear systems with constant coefficients

```ad-note
title:
This is just a linear system $$\dot{x}(t) = A(t)x(t)$$
But where $A(t)$ is a constant matrix valued function.
```

### For n=1:
$\dot{x} = kx \to x(t) = x(0)e^{kt}$

### For $n \geq 1$ uncoupled:
$$
\begin{align}
\dot{x_{1}}= \lambda_{1}x_{1} \\
\dot{x_{2}} = \lambda_{2}x_{2} \\
\vdots \\
\dot{x_{n}}= \lambda_{n}x_{n}
\end{align}
$$
This gives $\varphi_{j}(t) = e^{\lambda_{j}t}$.
Now general solution $\varphi(t) = c_{1}\varphi_{1}(t) + \dots + c_{n}\varphi_{n}(t)$
In this case, we had $$
A = \begin{bmatrix}
\lambda_{1} \\
& \lambda_{2}  \\ 
& & \lambda_{3} \\
& & & \ddots \\
& & & & \lambda_{n}
\end{bmatrix}
$$
### For $n\geq 1$, coupled:
Suppose $A$ is diagonalisable with all eigenvalues real.

Let $P^{-1}AP = \mathrm{diag}[\lambda_{1},\lambda_{2},\dots\lambda_{n}]$ and $v_{j}$ be an eigenvector corresponding to $\lambda_{j}$. We can reduce the coupled system to an uncoupled one as follows.

Let $y := P^{-1}x$, so that $\dot{y} = P^{-1} \dot{x} = P^{-1}Ax = P^{-1}APy \implies  \dot{y} = \mathrm{diag}[\lambda_{1},\lambda_{2},\dots, \lambda_{n}] y$
Thus $$
y(t) = \begin{bmatrix}
c_{1}e^{\lambda_{1}t}  \\
c_{2}e^{\lambda_{2}t} \\
\vdots \\
c_{n}e^{\lambda_{n}t}
\end{bmatrix}
\implies x(t) = Py(t) = P 
\begin{bmatrix}
c_{1}e^{\lambda_{1}t}  \\
c_{2}e^{\lambda_{2}t} \\
\vdots \\
c_{n}e^{\lambda_{n}t}
\end{bmatrix}
$$
### For the general case: 
The answer is exponential of the matrix A.

```ad-note
title: Theorem
Given $A \in M_n(\mathbb{R})$; $\dot{x} = Ax$ and $x(0) = x_0$ has the unique solution, $\varphi(t) = e^{At}x_0$.

```
##### Proof:
Let $\varphi(t) = e^{At}x_{0}$.
Then $$
\begin{align}
\dot{\varphi}(t) &= \lim_{ h \to 0 } \frac{\varphi(t+h)-\varphi(t)}{h} \\
&= \lim_{ h \to 0 } \frac{e^{(t+h)A}x_{0}- e^{tA}x_{0}}{h} \\
&= \left( \lim_{ h \to 0 } \frac{(e^{hA}-I)e^{tA}}{h} \right)x_{0}
\end{align}$$
This is due to the fact that $e^{X+Y} = e^{X}e^{Y}$ if $X,Y$ commute.
$$
\begin{align}  
\implies  \dot{\varphi}(t) &= \left(\lim_{ h \to 0 } \frac{e^{hA}-I}{h}\right) e^{tA}x_{0} \\
&= \left( \lim_{ h \to 0 } \sum\limits_{k=1}^{\infty} \frac{A^{k}h^{k-1}}{k!}\right) e^{tA}x_{0} \\
&=Ae^{tA}x_{0} = A\varphi(t) 
\end{align}
$$
So, $\varphi(t)$ satisfies the ODE and $\varphi(0) = x_{0}$.


---
# Related Problems

---
# References
[[Homogenous Linear Systems]]
[[Exponential of a Matrix]]

