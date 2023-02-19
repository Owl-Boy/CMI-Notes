202301041401

Type : #Note
Tags : [[Complex Analysis]]

---
# Cauchy-Reimann Equation

let $f: U\to \mathbb C$ be an [[Analytic Function#Analytic Function|analytic function]], $f(z) = u(z) + iv(z)$, where $u$ and $v$ are real functions.
On computing $f'$ in $2$ different ways
1. Along x-axis
   $$
   \begin{aligned}
   f'(z)&=\lim\limits_{h\to 0, h\in \mathbb R} \frac{f(z+h)-f(z)}h\\
   &= \lim\limits_{h\to 0}\frac{u(z+h)-u(z)}h + \iota\lim\limits_{h\to 0}\frac{v(z+h)-v(z)}h\\
   &=\frac{\partial u}{\partial x}(z) + \iota\frac{\partial v}{\partial x}(z)
   \end{aligned}
   $$
2. Along y-axis 
   $$
   \begin{aligned}
   f'(z)&=\lim\limits_{h\to 0, h\in \mathbb R} \frac{f(z+\iota h)-f(z)}{\iota h}\\
   &= -\iota\lim\limits_{h\to 0}\frac{u(z+\iota h)-u(z)}h + \lim\limits_{h\to 0}\frac{v(z+\iota h)-v(z)}h\\
   &=-\iota\frac{\partial u}{\partial x}(z) + \frac{\partial v}{\partial x}(z)
   \end{aligned}
   $$
By comparing the two we have 
$$
{\partial u \over \partial x} = {\partial v \over \partial y}, {\partial u \over \partial y} = -{\partial v \over \partial x}
$$
---

### Cauchy riemann + real differentiablity implies complex differentiability

```ad-note
title: Theorem
Given a function $f : \mathbb{R}^2 \to \mathbb{R}^2$, $f = (u,v)$ where $u,v : \mathbb{R} \to \mathbb{R}$ which is differentiable as a real function at the point $p$, such that $\dfrac{\partial u}{\partial x} = \dfrac{\partial v}{\partial y}$ and $\dfrac{\partial v}{\partial x} = -\dfrac{\partial u}{\partial y}$, then $f$ is differentiable at $p$ when thought of as a complex function.
```

#### Proof:
By real differentiability we get $$\lim\limits_{h \to 0} \dfrac{\|f(p+h)-f(p) - Ah\|}{\|h\|} = 0$$
For some real matrix $A$ which is a matrix whose corresponding linear transformation is just a rotation along with a scaling (look at how a rotation matrix looks like and how A looks, use cauchy riemann here). Since $A$ takes in a vector in $\mathbb{R}^2$, and spits out a rotated and scaled version of the same, we can emulate this with a complex number.
Suppose $A$ looks like $\begin{pmatrix} a & -b \\ b & a \end{pmatrix}$, then the corresponding complex number will be $a+bi$, we can check that $A \begin{bmatrix} h_1 \\ h2 \end{bmatrix}$ and $(a+bi)(h1+ih2)$ give the same vector in the plane, just in different ways of writing.
And so, we can rewrite the limit as 
$$\lim\limits_{h \to 0} \dfrac{\|f(z+h)-f(z) - (a+bi)h\|}{\|h\|} = 0$$
Here, $z$ denotes the complex number associated to $p$ and $h$ is a compex number as well.
Also notice that we can now drop the modulus signs since if a complex number's modulus approaches 0, the complex number itself approaches 0. So this gives that $f'(z) = a+bi$ and $f$ is complex differentiable there.


---
# Related Problems

---
# References
[[Analytic Function]]