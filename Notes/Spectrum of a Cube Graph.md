202308211128

type : #Example
tags : [[Algebraic Graph Theory]]

#  Spectrum of a Cube Graph
---
$$V(Q_{k})=\{(x_{1},x_{2},\dots,x_{k}):x_{i}\in\{0,1\}\}$$
and a edge between two vertices exits if they differ in exactly one component. Can also be thought as [[Hamming Distance]] being equal to $1$ iff edge exists.

We get $Q_{k+1}$ by taking two copies of $Q_{k}$ and add $0$ as a component to vertices of first one and $1$ as a component to the edges of the second one, and making an edge between corresponding points.

The adjacency matrix of a cube graph is 
$$
A_{k+1}=
\begin{bmatrix}A_{k} & I \\ I & A_{k}\end{bmatrix}
$$
where $I=I_{2^{k}}$

**Claim**:  if $(\lambda, x)$ is an eigenpair of $Q_{k}$ then 
1. $(\lambda +1, y)$ is an eigenpair where $y$ is $\left[\frac{x}{x}\right]$
2. $(\lambda - 1, z)$ is an eigenpair where $z$ is $\left[\frac{-x}{x}\right]$
**Proof:**
1. $$
\begin{align*}
A_{k+1}y &= \begin{bmatrix}A_{k}x+x\\
x+A_{k}x\end{bmatrix}\\
&= \begin{bmatrix}\lambda x+x\\
x+\lambda x\end{bmatrix}\\
&= \lambda\begin{bmatrix}x\\
x\end{bmatrix}\\
&= \lambda y
\end{align*}
$$
Similar argument works for part 2
Using this we can get the spectra of cube graphs as
$$
\begin{align*}
\text{spectrum}(Q_{2})&= \begin{pmatrix}-2 & 0 & 2\\
1 & 2 & 1\end{pmatrix}\\
\text{spectrum}(Q_{3})&= \begin{pmatrix}-3 & -1 & 1 & 3\\
1 & 3 & 3 & 1\end{pmatrix}\\
\text{spectrum}(Q_{4})&= \begin{pmatrix}-4 & -2 & 0 & 2 & 4\\
1 & 4 & 6 & 4 & 1\end{pmatrix}\\
\end{align*}
$$


---
# Related


