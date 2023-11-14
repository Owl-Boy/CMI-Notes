---
tags:
  - Note
  - Incomplete
---
202310171510

Tags : [[Algorithmic Coding Theory]]

---
# Multivariate Polynomial Interpolation on Lines
Assume field $F$ is finite.
We have a multivariate polynomial $p:\mathbb{F}^{n}\to\mathbb{F}$ of total degree $d<|\mathbb{F}|$.
Fix any *line* $L_{\mathbf{u},\mathbf{v}}=\{\mathbf{u}+t\mathbf{v}|t\in\mathbb{F}\}\subset\mathbb{F}^{n}$.
Multivariate polynomial restricted to a line, 

## Simple fact
We can interpolate $p|_{L_{\mathbf{u},\mathbf{v}}}$ given its evaluations at any $d+1$ points on the line $L_{\mathbf{u},\mathbf{v}}$.

## Much stronger fact
We can interpolate $p$ on the line by a function that is both
- linear (the value of $p$ at any point on the line is a linear function of its values at $d+1$ other points on the line)
- "universal" (depends neither on $\mathbf{u},\mathbf{v}$ nor on $p$)

## Interpolating low-degree polys on lines
**Theorem:** For $d\in\mathbb{N}$, let $\mathbb{F}$ be a field of size $|\mathbb{F}|>d$. Then $\exists\alpha_{1},\dots,\alpha_{d+1}\in\mathbb{F}$ s.t. $\forall n\in\mathbb{N}$ and $\forall p:\mathbb{F}^{n}\to\mathbb{F}$ of total degree $d=deg(p)$ and every $\mathbf{u},\mathbf{v}\in\mathbb{F}^{n}$, it holds that $p(\mathbf{u})=\sum\limits_{i=1}^{d+1}\alpha_{i}p(\mathbf{u}+i\mathbf{v})$.

**Why is this surprising?**
Suppose we fix the polynomial $p$. It is not clear that for a fixed poly $p$ there exists a linear interpolation function that works for *every line!*

**Intuition:**
First consider the case when $d=1$.
For some $c_{0},\dots,c_{n}\in\mathbb{F}$, $p(\mathbf{w})=c_{0}+\sum\limits_{i\in[n]}c_{i}\mathbf{w}_{i}$.
Fix an arbitrary line $L_{\mathbf{u},\mathbf{v}}$ and consider two consecutive points in the line, $\mathbf{u}+t\mathbf{v}$, $\mathbf{u}+(t+1)\mathbf{v}$.
eg, $p(\mathbf{u})=2p(\mathbf{u}+\mathbf{v})-p(\mathbf{u}+2\mathbf{v})$

The **directional derivative** of $p$ in the direction of $\mathbf{v}$ of the line is constant.
$\Delta_{\mathbf{v}}p(\mathbf{w})=p(\mathbf{w}+\mathbf{v})-p(\mathbf{w})$
It reduces the degree of the polynomial by $1$.
For a pair of points $\mathbf{w},\mathbf{w}'$, (delta is the same for both)


---
# References
[[Reed-Muller Codes]]
[[Local Correcting and Decoding of RM codes]]
[[Local Decoding]]

