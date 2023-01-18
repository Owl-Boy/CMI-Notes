202301111401

Type : #Note
Tags : [[Complex Analysis]]

---
# Complex Polynomials


### Fundamental Theorem of Algebra
```ad-note
title:
Every polynomial $p(z)\in \mathbb C[z]$ has a root.
Hence, every polynomial factors into a product of linear polynomials.
```
A polynomial has a **Zero of order $m$**  at $a\in \mathbb C$ if $p(z) = (z-a)^m\cdot q(z)$ where $q(a) \ne 0$.

### Lucas Theorem
**Proposition:** If all zeroes of a polynomial lie in a half plane in $\mathbb C$, Then all zeroes of $p'(z)$ in it too. Which implies that if you take the convex hull of the zeroes of $p(z)$, inclusive of the boundary line, then all the roots of $p'(z)$ will all lie in size that.
**Proof:** Suppose $p(z)= (z-\alpha_1)\cdots(z-\alpha_n)$ 
Then 
$$
{p'(z)\over p(z)} = \frac1{z-\alpha_1}+\cdots+\frac1{z-\alpha_n}
$$
Suppose the half plane which contains the zeroes of $p(z)$ is 
$$
H:\frac{Im(z-a)}{b} < 0
$$
We have $\alpha_k\in H\forall k$, but suppose $z_0\in \mathbb C \setminus H$
$$
\begin{aligned}
{Im(z_0-\alpha_k)\over b}&= {Im(z_0-a)\over b}-{Im(z_0 - \alpha_k)\over b}\\
&\implies b(z_0-\alpha_k)^{-1}<0&\forall k\\
\implies Im(b)\frac{p'(z_0)}{p(z_0)} &= Im\frac{b}{z-\alpha_1}+\cdots+Im\frac{b}{z-\alpha_n}<0\\
&\implies p'(z_0)\ne 0
\end{aligned}
$$

---
# Related Problems

---
# References
[[Analytic Function]]