202301041401

Type : #Note
Tags : [[Complex Analysis]]

---
# Analytic Function

### Complex Derivative
```ad-note
title: 
let $f:U\to\mathbb C$ where $U$ is an open subset of $\mathbb C$, then the derivative of $f$ exists at $a\in U$ if the following limit exists
$$
\lim_{z\to a}\frac{f(z)-f(a)}{z-a}
$$
```

If $f, g$ are differentiable at $a$ then $f\pm g, fg$ are differentiable; $\frac fg$ is differentiable at $a$ if $g(a)\ne 0$

### Analytic Function
```ad-note
title:
A function $f:U\to \mathbb C$ is said to be **Analytic**(or **Holomorphic**) if $f'(z)$ exists $\forall z\in U$
```
Some examples are
- Identity Function
- Constant Functions
- [[Complex Polynomials|Polynomials]]
- [[Complex Rational Functions|Rational Functions]] (away from zeros of divisors)
- [[Power Series]]

*Proposition:* If $u(x, y), v(x, y)$ have first order partial deriavtives which satisfy the [[Cauchy-Reimann Equation| CR Equations]], then $f=u+\iota v$ is analytic with continuous partial derivative
_Proof:_
We may write $u(x+h, y+k) - u(x, y) = {\partial u \over \partial x}h+{\partial u \over \partial x}k + \epsilon_1$  
and $v(x+h, y+k) - v(x, y) = {\partial b \over \partial x}h+{\partial v \over \partial x}k + \epsilon_2$
such that $\epsilon_i \over n + \iota k$ $\to 0$ as $n+\iota k \to 0$ 
$$
\begin{aligned}
f(z+h + ik) - f(z) &= \left(\frac{\partial u}{\partial x} + \iota\frac{\partial v}{\partial x}\right)\cdot(h+\iota k)+\epsilon_1 + \epsilon_2\\
\frac{f(z+h+\iota k) - f(z)}{h + \iota k} &= \left(\frac{\partial u}{\partial x} + \iota\frac{\partial v}{\partial x}\right) + \frac{\epsilon_1 + \epsilon_2}{h+\iota k}\\
\implies f'(z) &= \frac{\partial u}{\partial x} + \iota\frac{\partial v}{\partial x}
\end{aligned}
$$
${\partial u \over \partial x}, {\partial v \over \partial x}$ are continuous, Hence $f'(x)$ is continuous.

---
# Related Problems

#### exercise:
If $f:\mathbb{C} \to \mathbb{R}$ is a function such that $f'(a)$ exists then show that $f'(a) = 0$.

---
# References
