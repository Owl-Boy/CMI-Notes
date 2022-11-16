2022-11-13 02:11 pm

Type : #Note
Tags : [[Analysis]]

---
# Good Kernels
```ad-note
title: Definition
Let $\{K_n\}$ be a sequence of functions defined on $\mathbb{T}$ satisfying:
- $\dfrac{1}{2\pi} \displaystyle\int_{-\pi}^{\pi} K_n(t)dt = 1  \ \forall \ n \ge 1$
- $\exists M > 0, \ s.t.\ \displaystyle\int\limits_{-\pi}^{\pi}|K_n(t)| \le M$
- $\forall \ \delta > 0, \displaystyle\int\limits_{\delta \le |x| \le \pi} |K_n(x)|dx \to 0 \ as\ n \to \infty$

Such a sequence of functions is called a family of *good kernels* or *approximate identity*.
```

--- 
## Properties:
```ad-note
title: Proposition
If $f$ is integrable over $\mathbb{T}$, and $\{K_n\}$ be a family of good kernels, then: 
	  $$lim_{n\to\infty} (f*K_n)(x) = f(x) \ \forall \ x$$
	 where $f$ is continuous at x. If $f$ is continuous on $\mathbb{T}$, then the convergence is uniform.
```
### Proof:
- Look at $|(f*K_n)(x) - f(x)|$, write it as $\displaystyle\left|\dfrac{1}{2\pi} \int \limits_{-\pi}^{\pi}(f(x-y)-f(x))K_n(y)dy\right|$
- Split this up into $[-\pi,-\delta],[-\delta,\delta],[\delta,\pi]$ 
- Show that each of them is small.

---
```ad-note
title: Proposition
The [[Dirichlet Kernels]] are not good kernels.
```
## Proof:
- They violate the second property of good kernels.
- Use $D_N(x) = \dfrac{sin(N + 1/2)x}{sin(x/2)}$
- $A = \int |D_N(x)| \ge 2\int \dfrac{|sin(N+1/2)x|}{x}dx \ge 4\int_0^{\pi}\left|\dfrac{sin(N+1/2)x}{x}\right|dx$
- change variables, $y = (N+1/2)x$
- $A \ge 4\int_0^{(N+1/2)\pi} \dfrac{|sin(y)|}{|y|}dy$ 
- break this up into integrals from $k\pi$ to $(k+1)\pi$
- and get a sum of the form 1 + 1/2 + 1/3 ... + 1/N
- $\displaystyle \int_{-\pi}^{\pi}|D_N(x)|dx \ge c\log(N) \ as \ N \to \infty$

---
# Related Problems
```ad-note
title: Examples
[[Fejer Kernel]]
```

---
# References
[[Convolutions]]
[[Dirichlet Kernels]]