2022-11-16 00:31 am

Type : #Note
Tags : [[Analysis]]

---
# Fourier series is the best approximation

```ad-note
title: Fourier Series is the best trig approximation
Suppose $s_N(f)(x) = \sum\limits_{m=-N}^{N}c_m\phi_m$ and $t_N(x) = \sum\limits_{m=-N}^{N}d_m\phi_m$ is another partial sum of a series converging to $f$.
Then $$\int\limits_{-\pi}^{\pi}|f-s_N|^2dx \le \int\limits_{-\pi}^{\pi}|f-t_N|^2dx$$
and $$\sum\limits_{m=-N}^{N}|c_m|^2 \le \int\limits_{-\pi}^{\pi} |f|^2dx$$
Where $\phi_m(x) = \dfrac{1}{\sqrt{2\pi}} e^{imx};\ m \in \mathbb{Z}$
```


---
# Related Problems
[[Convergence of Fourier Series]]
[[Uniqueness of fourier series]]

---
# References
[[Fourier Series]]
[[Dirichlet Kernels]]