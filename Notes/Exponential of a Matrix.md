202303121503

Type : #Note
Tags : [[Differential Equations]] [[Algebra]]

---
# Exponential of a Matrix
```ad-note
title:
Given $A \in M_n(\mathbb{R})$; we would like to define
$$e^A := \sum\limits_{n=0}^\infty \dfrac{A^k}{k!}$$
```
To make sure that the definition makes sense, we need to ensure that the series always converges.

We put a metric on $M_{n}(\mathbb{R})$ induced by the norm $\|A\| = \sup\limits_{\|x\| = 1} |Ax|$.
## Theorem
```ad-note
title:
$M_n(\mathbb{R})$ is complete under the metric induced by $\| \cdot \|$.
```
##### Proof:
Let $\{ T_{k} \}_{k \in \mathbb{N}}$ be a cauchy sequence in $M_{n}(\mathbb{R})$ i.e.,
$\forall \ \epsilon>0, \exists N_{0}$ s.t. $\forall \ k,n > N_{0}, \ \|T_{k}-T_{n}\| < \epsilon$.

Given any $x_{0}\in \mathbb{R}^{n}$, define $x_{j} := T_{j}x_{0}\ ,\  j\ge 1$.
Then for $k,n > N_{0}$ as above, $$
|T_{k}x_{0}-T_{n}x_{0}| \le \|T_{k}-T_{n}\| |x_{0}| < \epsilon|x_{0}|
$$
Thus the sequence of points $T_{j}x_{0}$ forms a cauchy sequence in $\mathbb{R}^{n}$.
Since $\mathbb{R}^{n}$ is complete, $\lim_{ j \to \infty }x_{j} = y_{x_{0}} \in \mathbb{R}^{n}$.
Define $\mathcal{M} : \mathbb{R}^{n} \to \mathbb{R}^{n}$ by $\mathcal{M}(x) = y_{x}$ by the above process. Show that this is a linear transform.
Then verify that $T_{j} \to \mathcal{M}$ as $j\to \infty$. $\square$

## Theorem
```ad-note
title:
Given $B \in M_{n}(\mathbb{R})$; the series $$e^B := \sum\limits_{k=0}^{\infty} \frac{1}{k!}B^{k}$$
converges in $M_{n}(\mathbb{R})$.
```
##### Proof:
Show that this sequence of partial sums is cauchy.

## Theorem
```ad-note
title:
Let $T_{1},T_{2} \in M_{n}(\mathbb{R})$ s.t. $T_{1}T_{2} = T_{2}T_{1}$, then $e^{T_{1}+T_{2}} = e^{T_{1}}e^{T_{2}}$
```
##### Proof:
$$
\begin{align}
e^{T_{1}}e^{T_{2}} &= \left( \sum\limits_{n=0}^{\infty} \frac{T_{1}^{n}}{n!}\right) \left( \sum\limits_{n=0}^{\infty} \frac{T_{2}^{n}}{n!} \right)  \\
&= \sum\limits_{n=0}^{\infty}\sum\limits_{k=0}^{n} \dfrac{T_{1}^{k}T_{2}^{n-k}}{k!(n-k)!} \\
&=  \sum\limits_{n=0}^{\infty} \frac{(T_{1}+T_{2})^{n}}{n!} \\
&= e^{T_{1}+T_{2}}
\end{align}
$$
---
# How do you calculate the exponential?
### 1. Exponential of a diagonal matrix
$$
A = \begin{bmatrix}
\lambda_{1}  \\
& \lambda_{2}  \\
	 &  & \ddots \\
	 &  &  & \lambda_{n}
\end{bmatrix}
\implies A^{k} = \begin{bmatrix}
\lambda_{1}^{k}  \\
& \lambda_{2}^{k}  \\
	 &  & \ddots \\
	 &  &  & \lambda_{n}^{k}
\end{bmatrix}
\implies e^{A} = \begin{bmatrix}
\sum \limits_{k=0}^{\infty} \frac{\lambda_{1}^{k}}{k!}  \\
	 & \sum \limits_{k=0}^{\infty} \frac{\lambda_{2}^{k}}{k!} \\
	 &  & \ddots  \\
	 &  &  & \sum \limits_{k=0}^{\infty} \frac{\lambda_{n}^{k}}{k!}
\end{bmatrix}
= \begin{bmatrix}
e^{\lambda_{1}}  \\
	 & e^{\lambda_{2}} \\
	 &  & \ddots  \\
	 &  &  & e^{\lambda_{n}}
\end{bmatrix}
$$
### 2. Exponential of a diagonalisable matrix
Given $A\in M_{n}(\mathbb{R})$, let $P \in GL_{n}(\mathbb{R})$ s.t. $$
P^{-1}AP = \mathrm{diag}[\lambda_{1},\lambda_{2},\dots ,\lambda_{n}]
$$
Then $(P^{-1}AP)^{k} = \mathrm{diag}[\lambda_{1}^{k},\lambda_{2}^{k},\dots,\lambda_{n}^{k}] = P^{-1}A^{k}P$
Hence, $$
e^{A} = \sum \limits_{ k=0}^{ \infty } \frac{A^{k}}{k!} = \sum \limits_{ k=0}^{ \infty } \frac{1}{k!}P\ \mathrm{diag}[\lambda_{1}^{k},\lambda_{2}^{k},\dots,\lambda_{n}^{k}] P^{-1} = P\left(\sum\limits_{ k=0}^{ \infty } \mathrm{diag}[\lambda_{1}^{k}, \lambda_{2}^{k},\dots , \lambda_{n}^{k}] \right) P^{-1}
$$
This gives $e^{A} = P \ \mathrm{diag}[e^{\lambda_{1}}, e^{\lambda_{2}},\dots , e^{\lambda_{n}}]P^{-1}$.

### 3. Exponential of a nilpotent operator
Suppose $A^k = 0 \ \forall \ k\ge N$
$$
e^{A} = \sum\limits_{ i=0}^{ N-1 } \frac{A^{i}}{i!}
$$
#### Note: A property: $e^{-A} = (e^{A})^{-1}$ (follows from $e^{X+Y} = e^{X}e^{Y}$ when $X,Y$ commute).

### 4. Exponential of 2x2 matrices.
**CASE 1:**
Let $A = \begin{bmatrix} a & b\\0 & a\end{bmatrix}$.
$A = aI + b \begin{bmatrix}0  &  1 \\ 0  & 0\end{bmatrix}$
Since $I$ and $\begin{bmatrix}0  &  1 \\ 0  & 0\end{bmatrix}$ commmute,
$$
e^{A} = e^{aI + b \begin{bmatrix}0  &  1 \\ 0  & 0\end{bmatrix}} = e^{aI} \cdot e^{b\begin{bmatrix}0  &  1 \\ 0  & 0\end{bmatrix}}
$$
But $\begin{bmatrix}0  &  b \\ 0  & 0\end{bmatrix}$ is nilpotent, hence $e^{\begin{bmatrix}0  &  b \\ 0  & 0\end{bmatrix}} = I + \begin{bmatrix}0  &  b \\ 0  & 0\end{bmatrix} = \begin{bmatrix}1  &  b \\ 0  & 1\end{bmatrix}$
Hence, $e^{A} = e^{a}\cdot \begin{bmatrix}1  &  b \\ 0  & 1\end{bmatrix}$. 

**CASE 2:**
Let $A = \begin{bmatrix}a  &  -b \\ b &  a\end{bmatrix}$.
The eigenvectors for $A$ are $\begin{bmatrix}1 \\ -i\end{bmatrix}$ and $\begin{bmatrix}1 \\ i\end{bmatrix}$ with eigenvalues $a+ib$ and $a-ib$ respectively.
So, $$
\begin{align}
\begin{bmatrix}
1 & 1 \\
-i & i
\end{bmatrix}^{-1}
\begin{bmatrix}
a & -b \\
b & a
\end{bmatrix} 
\begin{bmatrix}
1 & 1 \\
-i & i
\end{bmatrix} &= \begin{bmatrix}
\lambda & 0 \\
0 & \bar{\lambda}
\end{bmatrix} \\
\implies 
\begin{bmatrix}
1 & 1 \\
-i & i
\end{bmatrix}^{-1}
\begin{bmatrix}
a & -b \\
b & a
\end{bmatrix} ^{k}
\begin{bmatrix}
1 & 1 \\
-i & i
\end{bmatrix} &= \begin{bmatrix}
\lambda^{k} & 0 \\
0 & \bar{\lambda}^{k}
\end{bmatrix}  \\
\implies \begin{bmatrix}
a & -b  \\
b & a  
\end{bmatrix}^{k}
&=
\begin{bmatrix}
1 & 1 \\
-i & i
\end{bmatrix}
\begin{bmatrix}
\lambda^{k} & 0 \\
0 & \bar{\lambda}^{k}
\end{bmatrix}
\begin{bmatrix}
1 & 1 \\
-i & i
\end{bmatrix}^{-1} \\
&= \begin{bmatrix}
\mathrm{Re}(\lambda^{k})  & -\mathrm{Im}(\lambda^{k}) \\
\mathrm{Im}(\lambda^{k}) & \mathrm{Re}(\lambda^{k})
\end{bmatrix} 
\end{align}
$$
This gives $$
e^{A} = \begin{bmatrix}
\mathrm{Re}(e^{\lambda}) & -\mathrm{Im}(e^{\lambda}) \\
\mathrm{Im}(e^{\lambda})  & \mathrm{Re}(e^{\lambda})
\end{bmatrix}
$$
But $\lambda = a+ib$, $e^{\lambda} = e^{a}e^{ib} = e^{a}(\cos b + i\sin b)$.
This gives, $$
e^{A} = e^{a} \begin{bmatrix}
\cos b &  -\sin b \\
\sin b &  \cos b
\end{bmatrix}
$$

---
# Related Problems

---
# References
