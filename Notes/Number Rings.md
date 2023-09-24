202306021406

Type : #Note
Tags : [[Number Theory]]

---
# Number Rings
```ad-note
title:
A number ring is the ring of integers of a number field, in other words, the set of algebraic integers in the number field.
```

- An element of a number ring is a unit iff it has norm $\pm 1$.
- An element of a number ring is irreducible if its norm is a prime in $\mathbb{Z}$.
---
# Additive Structure of number rings
We are going to show that the number ring of a number field $K$ of degree $n$ over $\mathbb{Q}$ is a free group of rank $n$.

First note that given any basis of $K$ of $\mathbb{Q}$, we can multiply it by an integer such that the basis elements all lie in $R = \overline{\mathbb{Z}} \cap K$, this is possible since for any algebraic number there is an integer such that multiplying by it makes it an algebraic integer.

Fixing such a basis $\{ \alpha_{1},\dots,\alpha_{n} \} \subset R$ for $K$ over $\mathbb{Q}$, we have a free abelian group or rank $n$ inside $R$, namely,
$$
A = \mathbb{Z}\alpha_{1} \oplus \mathbb{Z}\alpha_{2} \oplus \dots \oplus \mathbb{Z}\alpha_{n}
$$
and this is abelian of rank $n$.

### Theorem 1
```ad-note
title:
Let $\{ \alpha_{1},\dots,\alpha_{n} \}$ be a basis for $K$ over $\mathbb{Q}$ consisting entirely of algebraic integers, and set $d = \mathrm{disc}(\alpha_{1},\dots,\alpha_{n})$. Then every $\alpha \in R$ can be expressed in the form 
$$
\frac{m_{1}\alpha_{1} + \dots m_{n}\alpha_{n}}{d}
$$
with all $m_{j} \in \mathbb{Z}$ and $d \mid m_{j}^{2}$.
```
###### Proof:
Let $\alpha = x_{1}\alpha_{1} + \dots + x_{n}\alpha_{n}$, $x_{i} \in \mathbb{Q}$. 
We need to show that $dx_{i} \in \mathbb{Z}$ for all $i$, and $d | d^{2}x_{i}^{2}$ or equivalently, $dx_{i}^{2} \in \mathbb{Z}.$
$\sigma_{i}(\alpha) = \sum_{j=1}^{n} x_{j}\sigma_{i}(\alpha_{j})$
Solving for $x_{j}$'s via cramer's rule gives $$
x_{j} = \frac{y_{j}}{|\sigma_{i}(\alpha_{j})|}
$$
where $y_{j}$ is the determinant of the matrix obtained by replacing the $j ^{th}$ column in $[\sigma_{i}(\alpha_{j})]$ by $\sigma_{i}(\alpha)$.

Thus $dx_{j} = \frac{dy_{j}}{|\sigma_{i}(\alpha_{j})|} = |\sigma_{i}(\alpha_{j})|y_{j} \in \overline{\mathbb{Z}}$, since $y_{j}, |\sigma_{i}(\alpha_{j})| \in \overline{\mathbb{Z}}$.
Thus $dx_{j} \in \mathbb{Q} \cap \overline{\mathbb{Z}} = \mathbb{Z}$. 
Now $dx_{j}^{2} \in \mathbb{Q} \cap \overline{\mathbb{Z}} = \mathbb{Z}$.

#### Thus, we get $A \subset R \subset \mathbb{Z}\frac{\alpha_{1}}{d} \oplus \mathbb{Z} \frac{\alpha_{2}}{d} \oplus \dots \oplus \mathbb{Z} \frac{\alpha_{n}}{d}$. Thus $R$ is sandwiched between two free groups of rank $n$, thus it has rank $n$ (refer [[Free Group]]). Equivalently, $R$ has a basis over $\mathbb{Z}$, this basis is called an **integral basis** for $R$.

---
# Discriminant of a number ring
### Theorem 2:
```ad-note
title:
Let $\{ \beta_{1},\dots,\beta_{n} \}$ and $\{ \gamma_{1},\dots,\gamma_{n} \}$ be two integral bases for $R = \overline{\mathbb{Z}} \cap K$. Then $\mathrm{disc}(\beta_{1},\dots,\beta_{n}) = \mathrm{disc}(\gamma_{1},\dots ,\gamma_{n}).$
```
###### Proof:
Writing the $\beta$'s in terms of the $\gamma$'s, we get $$
\begin{pmatrix}
\beta_{1}  \\
\beta_{2} \\
\vdots \\
\beta_{n}
\end{pmatrix} = 
M
\begin{pmatrix}
\gamma_{1} \\
\gamma_{2} \\
\vdots \\
\gamma_{n}
\end{pmatrix}
$$
This gives $$
[\sigma_{i}(\beta_{j})] = M [\sigma_{i}(\gamma_{j})] \implies \mathrm{disc}(\beta) = |M|^{2}\mathrm{disc}(\gamma)
$$
Thus $$
\frac{\mathrm{disc}(\beta)}{\mathrm{disc}(\gamma)}, \frac{\mathrm{disc}(\gamma)}{\mathrm{disc}(\beta)} \in \mathbb{Z}
$$
Thus $\mathrm{disc}(\beta)=\mathrm{disc}(\gamma)$.

#### Therefore, the discriminant of an integral basis can be regarded as an invariant of the ring $R$. Denote it by $\mathrm{disc}(R)$.

### Proposition 1:
```ad-note
title:
Assuming $\alpha_{1},\dots,\alpha_{n} \in R$, they form an integral basis iff $\mathrm{disc}(\alpha_{1},\dots,\alpha_{n}) = \mathrm{disc}(R)$.
```
###### Proof:
One direction is clear.
For the other direction, write $\alpha_{i}$'s in terms of an integral basis, which, following the proof of theorem 2, gives $$
\mathrm{disc}(\alpha_{1},\dots,\alpha_{n}) = |A|^{2}\mathrm{disc}(R)
$$where $A \in M_{n}(\mathbb{Z})$.
Since the discriminants are equal by assumption, $|A| = \pm {1}$, and hence $A$ is invertible, giving the original integral basis in terms of the $\alpha_{i}$'s, which means $\alpha_{1},\dots,\alpha_{n}$ forms an integral basis.

### Theorem 3:
```ad-note
title:
Given 2 number fields $K,L$ and their respective number rings $R,S$. And let $T$ be the number ring of the composite field $KL$, then $RS \subset T$. 

Let $[K:\mathbb{Q}] = m, [L :\mathbb{Q}] = n$, $d = \mathrm{gcd}(\mathrm{disc} \ R, \mathrm{disc} \ S)$.
Assume $[KL : \mathbb{Q}] = mn$ then $T \subset \frac{1}{d}RS$.
```
###### Proof:
The first part that $RS \subset T$ is clear.

### Lemma 1:
```ad-note
title:
Given an embedding $\sigma$ of $K$ in $\mathbb{C}$, and $\tau$ of $L$ in $\mathbb{C}$, there is an extension of $\sigma$ to $KL$, such that its restriction to $L$ is $\tau$.
```
###### Proof:
Since there are $n$ distinct extensions of $\sigma$ to $KL$, they must all be distinct on $L$ since any automorphism on $KL$ is determined by its action on $K$ and $L$ separately.
Thus there are $n$ possible restrictions to $L$ and one of them must be $\tau$ since there are exactly $n$ possible embeddings of $L$ in the first place.

Continuing with the proof of the theorem, let $\alpha \in T$ be any element, then $$
\alpha = \sum_{i,j} \frac{m_{ij}\beta_{i}\gamma_{j}}{r}
$$
where $\{ \beta_{1},\dots,\beta_{m} \}$ is the integral basis for $R$, and $\{ \gamma_{1},\dots,\gamma_{n} \}$ is the integral basis for $S$, and $m_{ij} \in \mathbb{Z}$, with $\mathrm{gcd}(r,\mathrm{gcd}(m_{ij})) = 1$. (This follows from Theorem 1, and the fact that $\{ \beta_{i}\gamma_{j} \}$ is a basis for $KL$ consisting of algebraic integers.)

Now we need to show that $d\alpha \in RS$. It suffices to show that $r \mid d$ which is equivalent to showing that $r \mid \mathrm{disc}(R), \mathrm{disc}(S)$. 
We show $r \mid \mathrm{disc}(R)$ and the other one is symmetric.

Let $\{ \sigma_{k} \}_{k=1}^{m}$ be a set of embeddings of $KL$ in $\mathbb{C}$ which fixes $L$ pointwise (possible by lemma 1).
$$
\begin{align}
\sigma_{k}(\alpha) &= \sum \frac{m_{ij}}{r}\sigma(\beta_{i})\gamma_{j} \\
\text{let } x_{i} &= \sum_{j=1}^{n} \frac{m_{ij}}{r}\gamma_{j}  \\
\text{then } \sigma_{k}(\alpha) &= \sum_{i} \sigma_{k}(\beta_{i})x_{i} \\
\implies \begin{bmatrix}
\sigma_{1}(\alpha) \\
\vdots \\
\sigma_{m}(\alpha)
\end{bmatrix}
&= \begin{bmatrix}
\sigma_{i}(\beta_{j})
\end{bmatrix} \begin{bmatrix}
x_{1} \\
\vdots \\
x_{m}
\end{bmatrix}
\end{align}
$$
Now applying cramer's rule, 
$$
x_{i} = \frac{y_{i}}{\delta}
$$
where $y_{i}$ is the determinant of the matrix $[\sigma_{i}(\beta_{j})]$ with the $i ^{th}$ column replaced by $\sigma_{j}(\alpha)$'s.
And $\delta = |\sigma_{i}(\beta_{j})|$.

We also know $\delta^{2} = \mathrm{disc}(R)$, $x_{i}\delta^{2} = y_{i}\delta \in \overline{\mathbb{Z}}$ since $y_{i}, \delta \in \overline{\mathbb{Z}}$.
Thus, $x_{i}\mathrm{disc}(R) = \sum_{j}\mathrm{disc}(R) \frac{m_{ij}}{r}\gamma_{j} \in \overline{\mathbb{Z}} \cap L = S$. 
Giving $r \mid \mathrm{disc}(R)m_{ij} \implies r \mid \mathrm{disc}(R)$.

### Corollary 1:
```ad-note
title:
If $[KL : \mathbb{Q}] = mn$ and $d = 1$ then $T = RS$.
```

### Corollary 2:
```ad-note
title:
Let $K = \mathbb{Q}(\omega), \omega = e ^{2\pi i/m}, R = \overline{\mathbb{Z}}\cap K$. Then $R = \mathbb{Z}[\omega]$.
```
###### Proof:
Refer to [[Cyclotomic Fields]], theorem 3.

---
### Theorem 4: 
```ad-note
title:
Let $\alpha \in R$ and suppose $\alpha$ has degree $n$ over $\mathbb{Q}$. Then there is an integral basis 
$$
1, \frac{f_{1}(\alpha)}{d_{1}}, \dots \frac{f_{n-1}(\alpha)}{d_{n-1}}
$$
where the $d_{i} \in \mathbb{Z}$ and satisfy $d_{1}  \mid d_{2}\mid\dots\mid d_{n-1}$; the $f_{i}$ are monic polynomials over $\mathbb{Z}$, and $f_{i}$ has degree $i$. The $d_{i}$ are uniquely determined.
```
###### Proof:
For each $k, 1\le k\le n$ let $F_{k}$ be the free abelian group of rank $k$ generated by $1/d, \alpha/d, \dots \alpha^{k-1}/d$, where $d = \mathrm{disc}(\alpha)$, and set $R_k = R \cap F_{k}$. 
Thus we have $R_1 = \mathbb{Z}$ and $R_n = R$. 
We will define the $d_{i}$ and the $f_{i}$ so that for each $k, 1 \le k \le n$, $1, f_1(\alpha)/d_1 , \cdots , f_{k−1}(\alpha)/d_{k−1}$ is a basis over $\mathbb{Z}$ for $R_{k}$.
This is certainly true for $k = 1$. 
Thus fix $k < n$ and assume that $\{1, f_1(\alpha)/d_1, \cdots , f_{k−1}(\alpha)/d_{k−1}\}$ is a basis over $\mathbb{Z}$ for $R_{k}$, with the $f_i$ and $d_{i}$ as in the theorem. 
We have to define $f_{k}$ and $d_{k}$ and show that we get a basis for $R_{k+1}$ by throwing in $f_{k}(\alpha) /d_{k}$. 

Let $\pi$ be the canonical projection of $F_{k+1} = \mathbb{Z} \frac{1}{d} \oplus \dots \oplus \mathbb{Z} \frac{\alpha^{k}}{d}$ on its last factor.
That is, $\pi$ selects the term of degree $k$. 

Then $\pi(R_{k+1})$ is a subgroup of the infnite cyclic group 
$$
\mathbb{Z} \frac{\alpha^{k}}{d} = \left\{  \frac{m\alpha^{k}}{d} : m \in \mathbb{Z}  \right\}
$$
which implies that $\pi(R_{k+1})$ is cyclic. 
Fixing any $\beta \in R_{k+1}$ such that $\pi(\beta)$ generates $\pi(R_{k+1})$, we see that $\{ 1,f_{1}(\alpha) /d_{1},\dots, f_{k-1}(\alpha) /d_{k-1}, \beta \}$ is a basis for $R_{k+1}$. Indeed, given any $\gamma \in R_{k+1}$, $\gamma = \left( \gamma - \frac{\beta\pi(\gamma)}{\pi(\beta)} \right) + \frac{\beta\pi(\gamma)}{\pi(\beta)}$, here $\gamma - \frac{\beta\pi(\gamma)}{\pi(\beta)} \in R_{k}$ and $\frac{\beta \pi(\gamma)}{\pi(\beta)} \in \mathbb{Z}\beta$.
Thus $R_{k+1} = R_{k} \oplus \mathbb{Z}\beta$.

It remains to show that β has the right form. 
We have $$\frac{\alpha^{k}}{d_{k-1}} = \pi\left( \frac{\alpha f_{k-1}(\alpha)}{d_{k-1}} \right)$$
and this is in $\pi(R_{k+1})$ since $\frac{\alpha f_{k-1}(\alpha)}{d_{k-1}} \in F_{k+1} \cap R$.
It follows that $\alpha^{k} /d_{k-1} = m \pi(\beta)$ for some $m \in \mathbb{Z}$.
Defining $d_{k} = md_{k-1}$, we get $\pi(\beta) = \frac{\alpha^{k}}{d_{k}}$ and so, $\beta = \frac{f_{k}(\alpha)}{d_{k}}$ for some monic polynomial $f_{k}$ of degree $k$.
But why does $f_{k}$ have integer coefficients?

We know that $df_{k} /d_{k}$ has integer coefficients, but since $f_{k}(\alpha) /d_{k-1} = m\beta \in R$, we have $$
\gamma = \frac{f_{k}(\alpha) - \alpha f_{k-1}(\alpha)}{d_{k-1}} \in R_k
$$
Using our basis for $R_{k}$, we have $\gamma = \frac{g(\alpha)}{d_{k-1}}$, for some $g(x)\in \mathbb{Z}[x]$ having degree < $k$.
This implies $g(x) = f_{k}(x)-xf_{k-1}(x)$.
And hence $f_{k} \in \mathbb{Z}[x]$.

Now observe that the conditions in the theorem imply that $d_{k}$ is the smallest positive integer $m$ such that $mR_{k+1} \subset \mathbb{Z}[\alpha]$.

---
# Properties of Number Rings
### Theorem 5:
```ad-note
title:
Every number ring is a dedekind domain.
```
###### Proof:
1. To prove that a number ring is noetherian, note that $R$ is a free abelian group of rank $n$ (say).
   Now any ideal $I$ is an additive subgroup of this group, hence is free of rank $m \le n$, and therefore it is finitely generated.
2. Take any ideal $I$ of $R$, and let $\alpha \in I$ be a non unit element.
   Now $N ^{K}(\alpha) = \alpha \cdot \alpha' = m$ where $K$ is the number field corresponding to the number ring $R$ and $\alpha'$ is the product of all the conjugates of $\alpha$ in $K$ except $\alpha$ itself.
   Note that $\alpha' \in K \cap \overline{\mathbb{Z}} = R$ and so, $m \in I$.
   This gives $R/(m) = m ^{n}$, and $|R /I| \le | R /(m)| = m ^{n}$.
   Thus if $I$ is a prime ideal, then $R /I$ is an finite integral domain, and so it is a field, and thus $I$ is a maximal ideal.
3. Let $\frac{\alpha}{\beta} \in K$ be a root of a monic poly over $R$. Then $\frac{\alpha}{\beta}$ is an algebraic integer by Theorem 3 of [[Algebraic Integers]].
   Thus $\frac{\alpha}{\beta} \in K \cap \overline{\mathbb{Z}} = R$.




---
# References
[[Number Field]]
[[Trace and Norm]]
[[Free Group]]
[[Cyclotomic Fields]]
[[Algebraic Integers]]
[[Dedekind Domains]]