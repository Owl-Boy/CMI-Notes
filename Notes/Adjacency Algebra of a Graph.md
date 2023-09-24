202308091108

Type : #Note
Tags : [[Algebraic Graph Theory]]

---
# Adjacency Algebra of a Graph
```ad-note
title:
Let $A$ be the adjacency matric os $G$
Then the adjacency algebra of $G$ is
$$
\mathcal A(G) = \sum\limits_{t} r_{t}A^{t} : r_{t}\in\mathbb R
$$
```

## Theorem
Let $d=diam(G)$, then $\dim(\mathcal A(G))>d$
## Proof
$\exists x,y\in V$ and $d(x,y)=d$
then $(A^{t})_{xy}=0$ for $t<d$ but it is $1$ for $t=d$
then 
$I, A, A^{2},\dots, A^{d}$ are linearly independent,
Assume 
$I, A, A^{2,\dots,}A^{d-1}$ are linearly independent
but $A^d$ is the only matrix with a non zero value at position (x,y).
Hence to add them to $0$ the coefficient of $A^{d}$ should be $0$.
To justify the assumption, given the above $x, y$ there exists $y'$ such that $d(x, y')=d-1$, which means the sum would be zero if coefficient of $A^{d-1}$ is $0$. Then induct down to nothingness.

## Theorem
Let $G$ have edges. then the following are equivalent:
1. $G$ is connected and $k-$regular for some $k\ge 0$ 
2. $J\in \mathcal A(G)$
## Proof
$(1\to 2)$
Let $m(x)=(x-k)q(x)$ be the minimal polynomial of $A$
we have $Aq(A)=kq(A)$
every column of $q(A)$ is an eigenvector corresponding to $k$ so every column is a multiple of $\hat j$ 
But since $kq(A)$ belongs to the _Adjacency Algebra_ its symmetric. hence the the matrix will be $xJ$.

$(2\to 1)$ 
given that $J$ is a polynomial in $\mathcal A$ we have that $J$ and $A$ commute.

Hence matrix containing column sums along a column is the same as the matrix containing row sums along the rows.

Thus $AJ=JA=kJ$ 
Existence of $J$ in the algebra also gives that the graph is connected.
As otherwise, relabel the vertices of $A$ such that vertices of connected components are together, then the adjacency matrix would look like blocks along diagonal and everything else is $0$, which means $J$ could not be in the algebra.

---
# References
[[Distances in Graphs]]