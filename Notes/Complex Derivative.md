202301041401

Type : #Note
Tags : [[Complex Analysis]]

---
# Complex Derivative
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
- Polynomials
- Rational Functions (away from zeros of divisors)

*Proposition:* If $u(x, y), v(x, y)$ have first order continuous partial derivatives which satisfy the [[Cauchy-Reimann Equation| CR Equations]], then $f=u+\iota v$ is analytic with continuous partial derivative.

---
# Related Problems

#### exercise:
If $f:\mathbb{C} \to \mathbb{R}$ is a function such that $f'(a)$ exists then show that $f'(a) = 0$.

---
# References
