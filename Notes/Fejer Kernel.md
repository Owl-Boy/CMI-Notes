2022-11-15 21:46 pm

Type : #Note
Tags : [[Analysis]]

---
# Fejer Kernel

```ad-note
title: Motivation
[[Dirichlet Kernels]] fail to be good kernels, but their averages are better behaved and are good kernels.
```

```ad-note
title: Definition
The N-th Fejer Kernel is defined by:
$$F_N(x) = \dfrac{D_0(x) + D_1(x) + \cdots D_{N-1}(x)}{N}$$
```

- Since $S_n(f) = f*D_n$, we can say that $\sigma_N(f)(x) = (f*F_N)(x)$ where $$\sigma_N(f)(x) = \dfrac{S_0(x) + S_1(x) + \cdots + S_{N-1}(x)}{N}$$
--- 
```ad-note
title: Proposition
We have a closed form for the Fejer Kernel, closely related to that of the [[Dirichlet Kernels]].
  $$F_N(x) = \dfrac{1}{N}\dfrac{\sin^2(Nx/2)}{\sin^2(x/2)}$$
```
### Proof:
  - Use $D_n(x) = \displaystyle\sum\limits_{j=-n}^{n}\omega^j = \dfrac{\omega^{-n}-\omega^{n+1}}{1-\omega}$where $\omega = e^{ix}$.
  - This gives $$F_N(x) = \dfrac{1}{N}\sum\limits_{n=0}^{N-1}\dfrac{\omega^{-n}-\omega^{n+1}}{1-\omega}$$$$ \implies F_N(x) = \dfrac{1}{N(1-\omega)}\sum\limits_{n=0}^{N-1}(\omega^{-n}-\omega^{n+1})$$
  $$ \implies F_N(x) = \dfrac{1}{N(1-\omega)^2}(\omega^{1-N}-2\omega+\omega^{N+1})$$
  $$ \implies F_N(x) = \dfrac{1}{N(\omega^{-1/2}-\omega^{1/2})^2}(\omega^{-N}-2+\omega^{N}) = \dfrac{1}{N(\omega^{-1/2}-\omega^{1/2})^2}(\omega^{-N/2}-\omega^{N/2})^2$$
  This gives the desired result.
  
---
```ad-note
title: Theorem
The Fejer Kernel is a good kernel.

```
### Proof: 
- The first property of good kernels can be verified, since it also holds for dirichlet kernels.
- The second property obviously holds because the first property holds and $F_N(x)$ is always positive.
- $sin ^2(x/2) \ge c_\delta > 0$ for all $\delta \le |x| \le \pi$ and so, $F_N(x) \le 1/Nc_\delta$ for such $x$. Which gives that $$\int\limits_{\delta\le|x|\le\pi} F_N(x) \to 0$$ as $N \to \infty$.

---
```ad-note
title: Theorem
If $f$ is integrable on the circle then the fourier series of $f$ is cesaro summable to $f$ at all points of continuity of $f$.
If $f$ is continuous, then it is uniformly cesaro summable to $f$.
```

### Proof:
This is a direct application of property (1) in [[Good Kernels]].

```ad-note
title: Corollary
Continuous functions on the circle can be approximated by trigonometric polynomials.
```
- This is closely related to the [[Weierstrass Approximation Theorem]].

---
# Related Problems
[[Dirichlet Kernels]]

---
# References
[[Good Kernels]]
[[Cesaro Summability]]
[[Dirichlet Kernels]]
[[Weierstrass Approximation Theorem]]


---
