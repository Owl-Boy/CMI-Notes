202301111401

Type : #Note
Tags : 

---
# Complex Rational Functions
Let 
$$
R(z)=\frac {P(z)} {Q(z)}
$$
be in its lowest term where $P,Q$ are [[Complex Polynomials]].
We may give $R(z)$ the value $\infty$ whenever $Q(z)=0$.
Then $R(z):\mathbb C\to S$ is continuous.

A point $a$ where $Q(z)$ has a zero is called a **pole** of if $R(z)$. Its order is the order of $a$ as a root of $Q(z)$

---
For greater unity, consider a map 
$R: S\to S$ and let $R_1(z)=R(\frac1z)$ 
then $R(\infty) = R_1(0)$
If $R_1(0) = 0$ or $\infty$ , then the order of the zero or pole of $R(z)$ at $\infty$ is defined as the order of the zero or pole of $R_1(z)$ at $0$
$$
\begin{aligned}
\text{Say } R(z) &= {a_0 + a_1z+\cdots+a_nz^n\over b_0+b_1z+\cdots+b_mz^m}\\
R_1(z) &= z^{m-n}{a_0z^n + a_1z^{n-1}+\cdots+a_n\over b_0z^m+b_1z^{m-1}+\cdots+b_m}\\
\end{aligned}
$$
If $m>n$,  $R(z)$ has a zero of order $m-n$ at $\infty$; if $m<n$, $R(z)$ has a pole of order $n-m$ at $\infty$.

```ad-note 
title: Lemma
order($R$) = order($R-a$), $a \in \mathbb{C}$
```
This gives that order($R$) = $1 \implies R$ is injective. (Since if not then order($R-a) \ge 2$ for some $a$, but that's a contradiction to the lemma).
We will see that $R$ is surjective too.

This would imply that any $R(z) = \dfrac{az+b}{cz+d}$ , $ad-bc \neq 0$ (why? $R(z)$ becomes a constant otherwise) gives a bijective (analytic) function of $S \to S$.
$R^{-1}(z) = \dfrac{dz-b}{-cz+a}$ 

---
# Related Problems
[[Number Of Roots and Poles of a Rational Function]]
Find the group of 1-1 analytic self-homeomorphisms of $\mathbb{C}$. Assume that it is a subgroup of $SL_2(\mathbb{C})/\{\pm 1\}$.

---
# References
[[Analytic Function]]