202302151102

Type : #Note
Tags : [[Algebra]]

---
# Free Module
```ad-note
title:
A module M over a ring R is called _free_ if it has a basis.
```

- A module is free of _rank n_ if it has a basis of size n. (This is well defined)
- Submodules of free modules need not be free, but the next result shows it is true if R is a PID.

```ad-note
title: Proposition
Let R be a PID, let M be a free R module of finite rank n and let N be a submodule of M. Then 
1) N is free of rank m, $m \le n$
2) There is a basis $y_1,y_2,\cdots y_m$ of M such that $a_1y_1,\cdots a_my_m$ is a basis of N where $a_1,\cdots a_m$ are non zero elements of R such that $$a_1 | a_2 | \cdots | a_m$$
```

#### Proof:
The following proof is from _Dummit and Foote (Pg 460, Theorem 4)_.
```ad-info
title: Idea
The idea is to find a homomorphism from M to R, such that M can be written as a direct sum of its image and kernel, i.e. $M = R \oplus \mathrm{ker}(\nu)$, this allows us to induct. But then we also want $N = R \oplus \mathrm{ker}(\nu) \cap N$. So we try looking at all possible homomorphisms from N to R and try to pick that which fits.
Also, need $N = Ry_1 \oplus \mathrm{ker}{\nu}$ where $\nu(y_1) = 1$ but that might not be possible with $y_1 \in N$, but certainly is possible with $y_1 \in M$. So we try to see the smallest possible multiple of 1 that we can get for $\nu(y)$. That leads us to take the maximal element in $\Sigma$.
```

- Take the set of ideals $\Sigma = \{\phi(N) \ | \ \phi \in \mathrm{Hom}_R(M,R)\}$. Denote by $a_\phi$ the generator of the principal ideal $\phi(N)$.
- This is non empty since $(0)$ is in this collection, and there is a non trivial maximal element since R is noetherian and $(a_{\pi_i}) \neq (0)$ for some $\pi_i$ (projection map). 
- Take a maximal element from $\Sigma$, let this be $(a_\nu) = \nu(N)$. Rename $a_\nu = a_1$ and let $y \in N$ such that $\nu(y) = a_1$.
- Show that $a_1$ divides $\phi(y)$ for all $\phi \in \mathrm{Hom}_R(M,R)$.
- This gives $y = a_1y_1$ where $y_1 = \sum \limits_{i=1}^n b_i x_i$ where $x_1,x_2,\dots, x_n$ forms a basis for M.
- $\nu(y_1)=1$
- $M = Ry_1 \oplus \mathrm{ker}(\nu)$
- $N = Ra_1y_1 \oplus (\mathrm{ker}(\nu) \cap N)$
- Use induction to show that N is a free module (refer to [[Rank of a module]] to show that it is of rank at most m).

- Prove (2) by induction on n.
	- ker$(\nu)$ is free of rank n-1.
	- By induction hypothesis on ker$(\nu)$ and ker$(\nu) \cap N$, we get a basis $y_2,\dots y_n$ of ker$(\nu)$ such that $a_2y_2, \dots a_my_m$ is a basis of ker$(\nu)\cap N$ with the division condition.
	- This gives $y_1,\cdots y_n$ is a basis for M and $a_1y_1,\cdots a_my_m$ is a basis for N.
	- Define $\phi : M \to R$ by $\phi(y_1) = \phi(y_2) = 1$ and $\phi(y_i) = 0$. This gives $a_1 = \phi(a_1y_1) \in \phi(N)$, hence $(a_1) \subset \phi(N)$ but by the maximality of $(a_1)$ in $\Sigma$, we get that $(a_1) = \phi(N)$. Since $a_2 = \phi(a_2y_2) \in (a_1)$, $a_1 | a_2$. 

---
# Related Problems

---
# References
[[Principal Ideal Domain]]
[[Module]]
[[Rank of a module]]

