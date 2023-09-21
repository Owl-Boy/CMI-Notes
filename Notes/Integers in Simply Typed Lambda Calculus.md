202309071009

Type : #Note
Tags : [[Lambda Calculus]], [[Type Theory]]

---
# Integers in Simply Typed Lambda Calculus


To Give [[Church Numerals]] a type in simply typed lambda calculus. We try to figure out the types

$$
\begin{align*}
\lambda fx.x &: a\to b\to b\\
\lambda fx.fx &: (p\to q)\to p\to q\\
\lambda fx.f(fx) &: (p\to p) \to p \to p\\
\vdots
\end{align*}
$$
So we can define the type **Int** to be $(p\to p)\to p\to p$
Hence we can represent the functions $f:\mathbb N^{k}\to\mathbb N$ in terms of lambda terms.
$$
F c_{n_{1}}\dots c_{n_{k}} =c_{f(n_{1},\dots n_{k})}
$$
The class of *Extended Polynomials* is the smallest class of functions over $\mathbb N$ which is closed under composition, contains constant functions $0$ and $1$, projections, addition, multiplication and conditional statements

$$
\text{Cond}(n_{1}, n_{2}, n_{3}) = 
\left\{
\begin{align*}
n_{2} && \text{if }n=0\\
n_{3} && \text{otherwise}
\end{align*}\right.
$$

**Theorem(Schwichtenberg)**: The $\lambda_{\to}$-definable terms are exactly the extended polynomials.


---
# References
[[Expressive Power of Gödel's system T]]
[[Functions Computable in Lambda Calculus]]