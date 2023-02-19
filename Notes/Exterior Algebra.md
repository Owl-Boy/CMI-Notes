202210100910

Type : #Note
Tags : [[Calc]]

---
# Exterior Algebra
We define $\forall\ k$ a subspace
$$
\Lambda^k(V) \subset \mathcal T^k(V)
$$
And
$$
\Lambda^*(V) = \mathbb{R} \oplus \Lambda^1(V) \oplus \Lambda^2(V)\oplus\dots\oplus \Lambda^n(V)
$$
$\Lambda$ is a skew symmetric matrix
An element $A\in\Lambda^k(V)$ is a k-multilinear map such that
$$
A(v_{\sigma(1)}\dots v_{\sigma(n)}) = \text{sgn}(\sigma)A(v_1\dots v_n)
$$

_Lemma:_ $\dim \Lambda^k(V) = {n\choose k}$ if $0\le k \le n$  and $0$ if $k > n$ 
_Proof of Lemma:_ Let $k > n$ and let $A \in \Lambda^k(V)$ 
Choose a basis $(e_1\dots e_n)$
if $v_1\dots v_k$ are $k$ vectors is $V$
$$
\begin{aligned}
\text{write}\ \ v_i &= \sum \underbrace{v_{ji}}_{\in\mathbb{R}}e_j\\
\text{If}\ k > n, e_{ji_1} &= e_{ji_2} \text{ for some } i_1 \text{ and } i_2\\
\implies A(v_1\dots v_k) &= 0\\
\text{If } k &\le n\\ 
A(v_1\dots v_k) &= \sum \sum v_{j1}v_{j2}\dots A(e_{j1},e_{j2}\dots e_{jk})\\
\end{aligned}
$$
Which can be characterized by $A(e_{j1},e_{j2}\dots e_{jk})$
Hence $\dim \Gamma^k(V) = {n\choose k}$  

$$
\begin{aligned}
A&\in \Lambda^lV &\times B&\in\Lambda^mV &\times A\wedge B&\in\Lambda^{l+m}
\end{aligned}
$$
```ad-todo
Finish the diagram for types in multiplication in Exterior Algebra
```

We can use [[Alt]]: $\mathcal T^k(V) \to \Gamma^k(V)$ to get a multilinear map from $\Gamma^K(V)$ 

$$
A \wedge B = \frac{(l+m)!}{l!\times m!}\text{Alt}(A\otimes B)
$$
This product is Associative on $\Lambda^k(V)$, more precisely
$$
A\wedge (B\wedge C) = (A\wedge B)\wedge C
$$
Further
$$
A\wedge B = (-1)^{lm}B\wedge A
$$


```ad-info
title: Reason to study Exterior Algebra
[[Determinants]] of matrices form an Exterior Algebra which is a large part of why people study Exterior Algebra
```


---
# Related Problems
[[Calc - Problem Session - 7 Oct]]

---
# References

