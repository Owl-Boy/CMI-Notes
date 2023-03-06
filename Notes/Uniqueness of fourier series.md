2022-11-16 00:46 am

Type : #Note
Tags : [[Analysis]]

---
# Uniqueness of fourier series

```ad-note
title: Theorem
Suppose that $f$ is an integrable function on the circle with $\hat{f}(n) = 0$ for all $n \in \mathbb{Z}$.
Then $f(\theta_0) = 0$ whenever $f$ is continuous at the point $\theta_0$.
```

```ad-note 
title: Corollary
If $f$ is continuous on the circle and $\hat{f}(n) = 0 \ \forall \ n\in \mathbb{Z}$ then $f = 0$.
```

```ad-note
title: Corollary 
Suppose $f$ is continuous on the circle, and the fourier series of $f$ converges absolutely i.e., $\sum\limits_{n=-\infty}^{\infty}|\hat{f}(n)| < \infty$, then the fourier series converges uniformly to $f$, that is, $$\lim_{N\to\infty}S_N(f)(\theta) = f(\theta) $$ for all $\theta$.
```

### Proof: 
The function $g(\theta) = \sum \limits_{-\infty}^{\infty} \hat{f}(n)e^{in\theta}$ is the uniform limit of the functions $g_N(\theta) = \sum\limits_{-N}^{N}\hat{f}(n)e^{in\theta}$.
So, $g$ is continuous on the circle, and note that $\widehat{(f-g)}(n) = 0$, with $f-g$ continuous, this gives that $f = g$.

--- 

```ad-note
title: Corollary
Suppose $f$ is a $C^2$ function on the circle, then 
$$\hat{f}(n) = \mathcal{O}(1/|n|^2) \ as \ n \to \infty$$

so that the fourier series of $f$ converges absolutely and uniformly to $f$.
```

---
# Related Problems
[[Convergence of Fourier Series]]
[[Fourier series is the best approximation]]

---
# References
[[Fourier Series]]
