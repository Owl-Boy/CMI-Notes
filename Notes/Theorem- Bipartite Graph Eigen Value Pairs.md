202308091040

type : #Example
tags : [[Algebraic Graph Theory]]

#  Theorem- Bipartite Graph Eigen Value Pairs
---
## Theorem:
Let $G$ be _bipartite_. Then if $\lambda$ is an eigenvalue, so is $-\lambda$ with the same multiplicity
## Proof:
Let $A=\mathcal A(G)$. Then we can write $A$ in the form
$$
A =
\begin{bmatrix}O_{n_{1}\times n_{1}} & B_{n_{1}\times n_{2}} \\ B^{t} & O_{n_{2}\times n_{2}}\end{bmatrix}
$$
Let $(\lambda, z)$ be an eigenpair. let $z=\begin{bmatrix}x \\ y\end{bmatrix}$ 
$Az = \begin{bmatrix}By\\ B^{t}x \end{bmatrix}=\lambda z=\lambda \begin{bmatrix}x \\ y\end{bmatrix}$

So, $By = \lambda x$ and $B^{t}x = \lambda y$

We claim that $z'=\begin{bmatrix}-x \\ y\end{bmatrix}$ is an eigenvector for $-\lambda$
$Az' = \lambda \begin{bmatrix}x \\ -y\end{bmatrix}=-\lambda z$

The same process can be done for every single eigenvector for the eigenvalue $\lambda$ which gives the same multiplicity of $-\lambda$

---
# Related


