202210071156

type : #Example
tags : 

#  Calc - Problem Session - 7 Oct
---
 ### Question:
 Let $V$ be a real Vector space of dimension $n$
#### 1
Prove that $\dim V^* = n$ 
#### 2
Prove that $\dim \mathcal{T}^2(V) = n^2$
#### 3
Let $\Lambda^2(V)$ denote the Vector space of all bilinear antisymmetric maps, what is the dimension of $\Lambda^2(V)$?
#### 4
Define $\Lambda^k(V) \subset \mathcal{T}^k(V)$ suitably and find its dimension
#### 5
What about $S^k(V) \subset \mathcal{T}^k(V)$? where $S^k(V)$ is the space of all symmetic maps


---
###  Answer:
#### 1
Let $(e_1,e_2\dots e_n)$ be a bases for $V$
The linear form defined by 
$$
  \phi_i(e_j) =
    \begin{cases}
      1 & i = j \\
      0 & i\ne j 
    \end{cases} 
$$
Given $\phi \in V^*,\ v\in \sum\limits_{j=1}^na_je_j$ 
$$
\phi\left(\sum_{j=1}^na_je_j\right) = \sum_{j=1}^na_j\phi\left(e_j\right) = 
\sum_{j=1}^n\phi_j(v)\phi(e_j)= 
\left(\sum_{j=1}^nb_j\phi_j\right)(v) 
$$
where $b_j = \phi(e_j)$
Taking $\phi$ to be the zero map we get 
$$
\left(\sum_{i=1}^nb_i\phi_i\right)(e_j) = 0\implies b_j = 0\ \forall j 
$$
Thus the set of vectors spans $V*$ and is linearly independent.
Hence $\dim V = n$
#### 2
For $1 \le i, j \le n$, define $B_{ij}\in\mathcal{T}^2(V)$ by
$$
B_ij\left(\sum a_ie_i, \sum b_ie_i\right) = a_ib_j
$$
Given $B\in \mathcal{T}^2(V)$ define $b_{ij} = B(e_i, e_j)$

_Claim:_ B = $\sum_{i,j} b_{ij}B_{ij}$ 
$$
B\left(\sum a_ie_i, \sum b_ie_i\right) = 
\sum a_i \sum b_i\ B(e_i, e_j) = 
\sum B_{ij}(u,v)B(e_i,e_j) =
\sum b_{ij}B_{ij}(u,v)
$$
_Claim:_ $B_{ij}$  are linearly independent
Taking $B$ to be the zero map we get 
$$
\sum b_{ij}B_{ij}(e_l,e_m) = 0 = b_{lm}\ \forall\ l,m 
$$
$\therefore B_{ij}$ gvies a basis for $\mathcal{T}^2(V)$ 
$\therefore \dim \mathcal{T}^2(V) = n^2$
#### 3
Start with an antisymmetric bilinear map $A$
let $a_{ij} = A(e_i, e_j)\implies -a_{ij}$
Define a matrix $\tilde A$ to be a matrix with $\tilde a_{ij} = a_{ij}$ thus $\tilde A$ is antisymmetric  
Hence it is determined by $\frac{n(n-1)}2$
Therefore the span of $\Lambda^2(V) = \frac{n(n-2)}2$
#### 4
# TODO
#### 5
By similar construction as part 3, we get that $\dim S^2(V) =\frac{n(n+1)}2$
```ad-note
$$
\begin{aligned}
\dim S^2(V) + \dim \Lambda^2(V)&= dim \mathcal T^2{V} \\
S^2(V) \cap \Lambda^2(V) &= \emptyset\\
\implies S^2(V) \oplus \Lambda^2(V) &= \mathcal T^2(V)
\end{aligned}$$
This does not work for $k \ge 3$
$$\Lambda^k(V) \oplus S^k(V) \ne \mathcal T^k(V)\text( for )k\ge 3$$
```




---
# Related
[[Tensors]]

