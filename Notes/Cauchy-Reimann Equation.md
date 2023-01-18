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
# Related Problems

---
# References
[[Analytic Function]]