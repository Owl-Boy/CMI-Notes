2022-10-27 10:10 am

Type : #Note
Tags : [[Analysis]]

---
# Fourier Series

The fourier coefficients of a Riemann Integrable function $f$ defined on an interval $[a,b]$ are given by $$\hat{f}(n) = \dfrac{1}{b-a}\int_a^bf(x)e ^{-2\pi inx/(b-a)}dx$$We generally work with functions on the circle $\mathbb{T}$ and so, the fourier coefficients of function $f$ on the circle are given by:
$$\hat{f}(n) = \dfrac{1}{2\pi}\int_{-\pi}^{\pi}f(x)e ^{-inx}dx$$

---

## When does the fourier series converge?
It depends on the sense of the desired convergence.

For example, If we want uniform convergence, then we need $f$ to be a $C ^2$ function.

For pointwise convergence, we can't ensure that it holds for general Riemann Integrable $f$, since we can change the value of the function at a point, and the fourier coefficients still remain the same.
If we ensure that the function is continuous, even then we can't say in general that convergence will hold. (result by Du Bois-Reymond).

We can define the limit in the mean square sense, i.e, in the $L ^2$ norm.
If $f$ is just integrable, then $$\dfrac{1}{2\pi}\int_{-\pi}^{\pi}|S_Nf(\theta)-f(\theta)|^2d\theta$$

---
# Related Problems
[[Convergence of Fourier Series]]

---
# References
[[Uniqueness of fourier series]] 
[[Fourier series is the best approximation]]
[[Convergence of Fourier Series]]
