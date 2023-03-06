202301181401

Type : #Note
Tags : [[Complex Analysis]]

---
# Power Series
```ad-note
title:
A **Power Series** with center $z_{0\in}\mathbb C$ is a series of functions of the from
$$
\sum\limits_{n\ge0}a_{n}(z-z_0)^{n}
$$
```
[[Fourier Series]] is an example of power series in case of real functions
**Example:** Geometric Series
$$f(z)=\sum\limits_{n\ge0}z^n$$
We know that for all $z$ such that $|z|<1, f(z)$ [[Complex Convergence Results|converges]]

```ad-hint
title: Convention
The center of convergence is assumed to be $0$
```


**Theorem:** For every power series there is a radius of convergence, $R>0, R\in\mathbb R$ such that
1. For $|z|<R,\sum\limits a_nz^n$ converges absolutely and the series converges uniformly.
2. If $|z|>R,$ then $\sum\limits a_{n}z^{n}$ is divergent.
3. $|z|<R$, then $f(z)=\sum\limits a_{n}z^{n}$ is analytic, and the derivative is a power series whose terms are summation of derivative of terms of the power series. Further, the radius of convergence of the derivative of the power series is also $R$.
The circle $|z|=R$ is called the **Circle of Convergence**.
A formula for $R$ by Hadamard is 
$$
\frac1R=\limsup\limits_{n\to\infty}\sqrt[n]{|a_n|} 
$$


---
# Related Problems

---
# References
[[Analytic Function]]
