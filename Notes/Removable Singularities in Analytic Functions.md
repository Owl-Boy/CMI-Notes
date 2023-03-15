202303101503

Type : #Note
Tags : [[Complex Analysis]]

---
# Removable Singularities in Analytic Functions
Let $\Omega'$ be a region obtained by removing a point from the region $\Omega$, and $f$ is analytic on $\Omega'$, then
```ad-note
title: Theorem
$\exists!$ a function that agrees with $f$ on $\Omega'$ and is analytic on 
$Omega\iff\lim\limits_{z\to{a}}(z-a)f(z)=0$.
```

**Proof:** 
$\Longrightarrow$  Forward direction is trivial as the function in continuous at $a$
$\Longleftarrow$  Draw a circle $C$ inside $\Omega$ which contains $a$. Cauchy's formula is valid  hence we can write 
$$
	f(z)= \frac{1}{2i\pi}\int_{C} \frac{f(\zeta)d\zeta}{\zeta-z}
$$
for all $z\ne a$ inside of $C$. But the integral represents and analytic function of $z$ throughout the inside of $C$. Consequently, the functoin which is equal to $f(z)$ for $z\ne a$ and which has the value 
$$
	f(z)= \frac{1}{2i\pi}\int_{C} \frac{f(\zeta)d\zeta}{\zeta-a}
$$
for $z=a$ is analytic in $\Omega$.
$$
F(z)= \frac{f(z)-f(a)}{z-a}
$$
which isn't defined for $z=a$ but $\lim\limits_{z\to{a}}(z-a)F(z)=0$ and $\lim\limits_{z\to a} F(z)=f'(a)$
define $f_i$ in the following way
$$
\begin{align*}
\frac{f_i(z)-f_i(a)}{z-a}&= f_{i+1}(z)\\
\frac{f(z)-f(a)}{z-a}&= f_1(z)
\end{align*}
$$
from these equations we have 
$$
f(z)=f(a)+(z-a)f_{1}(a) + (z-a)^{2}f_{2}(a)+\dots+(z-a)^{n-1}f_{n-1}(a)+(z-a)^{n}f_{n}(z)
$$
on differentiating $n$ times, we have
$$f^{(n)}(a)=n!f_{n}(a)$$
This gives us the Taylor's theorem for analytic functions which states
$$
f(z) = f(a) + \frac{f'(a)}{1!}(z-a) + \frac{f''(a)}{2!}(z-a)^{2}+\dots+ \frac{f^{(n-1)}(a)}{(n-1)!}(z-a)^{n-1} +f_{n}(z)(z-a)^{n}
$$
where $f_{n}(z)$ is analytic in $\Omega$ 
$$
f_{n}(z) = \frac{1}{2i\pi} \int_{C} \frac{f_n(\zeta)d\zeta}{\zeta-z}
$$
by applying the taylor expansion to $F(z)$ we get
$$F_{\nu}(a)=\int_{C} \frac{d\zeta}{(\zeta-a)^{\nu}(\zeta-z)}$$
but $F_{1}(a)=0$. Hence
$$
f_{n}(z)= \frac{1}{z-a} \int_{C} \frac{f(\zeta)d\zeta}{(\zeta-a)^{n}(\zeta-a)}
$$
which is valid, hence $f(z)$ exists

---
# Related Problems

---
# References
