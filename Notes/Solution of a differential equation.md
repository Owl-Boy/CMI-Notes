202212131812

Type : #Note
Tags : [[Differential Equations]]

---
# Solution of a differential equation

```ad-note
title:
A function relation between the independent and the dependent variable which satisfies a differential equation is called the _Solution_ of the differential equation.
```

__Eq__: $xy'' + 3y = 6x^3$

The _General Solution_ of a $n^{th}$-order differential equation is dependent of $n$ arbitrary constants.
The general solution for __EQ__ is : $y = x^3 + {c \over x^3}$ while a $y = x^3$ is a _particular solution_ of __EQ__ which is obtianed by putting $c=0$.

A DE of first order can be written as $F(x, y, y') = 0$ and $y = \phi(x)$ is called an _Explicit Solution_ given $F(x, \phi(x), \phi'(x))=0$  

A relation of the form $\psi(x, y)=0$ is said to be an _Implicit Solution_ of $F(x, y, y')=0$ if it determines one or more function $y=\phi(x)$ which are explicit solutions. We can test an explicit solution by
$$\psi_x + \psi_yy'=0\implies y'=-\frac{\psi_x}{\psi_y}$$
and putting it in the equation
$$
F(x, y, -\frac{\psi_x}{\psi_y})=0
$$

A pair of equation $x=x(t),y=y(t)$ is called a _Parametric Equation_ if 
$$
F\left(x(t), y(t), \frac{dy/dy}{dx/dt}\right)=0
$$

---
# Related Problems
[[Solving a First Order ODE]]

---
# References
[[ODE]]