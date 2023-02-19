2022-11-16 00:26 am

Type : #Note
Tags : [[Analysis]]

---
# Convolutions
```ad-note
title: Definition
Given two $2\pi$-periodic integrable functions $f,g$ on $\mathbb{R}$, we define their convolution as follows:
$$(f*g)(x) = \dfrac{1}{2\pi} \int \limits_{-\pi}^{\pi}f(y)g(x-y)dy$$
```

- Partial sums of fourier series can be written as convolutions.
	  $$S_N(f)(x) \colon = \sum \limits_{-N}^{N} \hat{f}(n)e^{inx} =(f*D_N)(x)$$
- ### Properties:
1) $f*(g+h) = f*g + f*h$
2) $(cf)*g = c (f*g) = f*(cg) \ \forall c \in \mathbb{C}$
3) $f*g = g*f$
4) $(f*g)*h = f*(g*h)$
5) $f*g$ is continuous
6) $\widehat{(f*g)}(n) = \hat{f}(n)\hat{g}(n)$
---
# Related Problems
[[Good Kernels]]

---
# References
