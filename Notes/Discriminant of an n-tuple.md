202302281602

Type : #Note
Tags : [[Number Theory]]

---
# Discriminant of an n-tuple
```ad-note
title:
Let $K$ be a number field of degree $n$ over $\mathbb{Q}$. Let $\sigma_1,\dots,\sigma_n$ denote the n embeddings of $K \in \mathbb{C}$. For any $n$-tuple of elements $\alpha_1,\dots,\alpha_n \in K$, define the discriminant as follows:
$$\mathrm{disc}(\alpha_1,\dots,\alpha_n) = |\sigma_i(\alpha_j)|^2$$
where $|M|$ denotes the determinant of the matrix $M$.
```

### Theorem 1:
```ad-note
title: 
$$
\mathrm{disc}(\alpha_{1},\alpha_{2},\dots,\alpha_{n}) = \mid T(\alpha_{i}\alpha_{j})\mid
$$
```
### Proof:
$$
\begin{align}
\mathrm{disc}(\alpha_{1},\alpha_{2},\dots,\alpha_{n}) &= |\sigma_{j}(\alpha_{i})| |\sigma_{i}(\alpha_{j})| \\
&= \left|\sum_{k=1}^{n}\sigma_{k}(\alpha_{i})\sigma_{k}(\alpha_{j})\right| \\
&= | T(\alpha_{i}\alpha_{j})|
\end{align}
$$
### Corollary
```ad-note
title: 
If $\mathrm{disc}(\alpha_{1},\dots,\alpha_{n}) \in \mathbb{Q}$, and if all $\alpha_{i}'s$ are integers then $\mathrm{disc}(\alpha_{1},\dots,\alpha_{n}) \in \mathbb{Z}$.
```

### Theorem 2
```ad-note
title:
$\mathrm{disc}(\alpha_{1},\dots,\alpha_{n}) = 0$ iff $\alpha_{1},\dots,\alpha_{n}$ are linearly dependent over $\mathbb{Q}$.
```
### Proof:
If they are linearly dependent, then the columns of the matrix $[\sigma_{i}(\alpha_{j})]$ are too, hence discriminant is 0.
If disc is 0, then the rows of $[T(\alpha_{i}\alpha_{j})]$ are linearly dependent, hence there are $a_{1},a_{2},\dots,a_{n} \in \mathbb{Q}$ such that:
$$
a_{1}T(\alpha_{1}\alpha_{j}) + \dots + a_{n}T(\alpha_{n}\alpha_{j}) = 0
$$
for all $1 \le j \le n$.
Implying $T(\alpha_{j}(a_{1}\alpha_{1}+\dots+a_{n}\alpha_{n})) = 0$
Now if the $\alpha_{j}$ are linearly independent over $\mathbb{Q}$, they form a basis for $K$ over $\mathbb{Q}$, and $\alpha := a_{1}\alpha_{1} + \dots a_{n}\alpha_{n} \neq 0$.
Thus $\alpha\alpha_{j}$ forms a basis over $\mathbb{Q}$.
But then $T(\alpha\alpha_{j}) = 0$ for all $j$, implying $T(\beta) = 0$ for all $\beta \in K$, that's not true since $T(1) = n \neq 0$.
Contradiction.

### Theorem 3:
```ad-note
title:
Suppose $K = \mathbb{Q}(\alpha)$, and let $\alpha = \alpha_{1},\dots,\alpha_{n}$ denote the conjugates of $\alpha$ over $\mathbb{Q}$. Then 
$$
\mathrm{disc}(1,\alpha, \dots, \alpha^{n-1}) = \prod_{1 \le r < s \le n} (\alpha_{r}-\alpha_{s})^{2} = \pm N ^{K}(f'(\alpha))
$$
where $f$ is the minimal polynomial of $\alpha$ over $\mathbb{Q}$.
The plus sign holds iff $n \equiv 0 \ \text{or} \ 1 (\mathrm{mod}\ 4)$
```
###### Proof:
Note that $$
\begin{align}
\mathrm{disc}(1,\alpha, \dots,\alpha^{n-1}) &= |\alpha_{i}^{j}|^{2}  \\
&= \prod_{1 \le r < s \le n} (\alpha_{r}-\alpha_{s})^{2} \\
&= \pm\prod_{r \neq s} (\alpha_{r}-\alpha_{s})
\end{align}
$$
Since the determinant $|a_{i}^j|$ is a vandermonde determinant. There are $n(n-1)$ terms in the last product, and so, the plus sign holds iff $4 \mid n(n-1)$.
Now $f(x) = \prod_{i=1}^{n}(x-\alpha_{i})$ is the minimal poly of $\alpha$ over $\mathbb{Q}$.
Then $$
\begin{align}
f'(x) &= \sum_{j=1}^{n}\prod_{i\neq j}(x-\alpha_{i}) \\
\implies f'(\alpha) &= (\alpha-\alpha_{2})(\alpha-\alpha_{3}) \dots (\alpha-\alpha_{n}) \\
\implies N ^{K}(f'(\alpha)) &= \prod_{r=1}^{n}\sigma_{r}(f'(\alpha))  \\
&= \prod_{r=1}^{n}f'(\sigma_{r}(\alpha)) \\
&= \prod_{r=1}^{n}f'(\alpha_{r}) \\
&= \prod_{r=1}^{n}\prod_{r \neq s}(\alpha_{r}-\alpha_{s}) \\
&= \prod_{r \neq s}(\alpha_{r}-\alpha_{s})
\end{align}
$$
Thus we are done.

#### NOTE: We write $\mathrm{disc}(\alpha)$ to denote $\mathrm{disc}(1,\alpha, \dots ,\alpha^{n-1})$, for any algebraic number $\alpha$ of degree $n$ over $\mathbb{Q}$.

### Theorem 4:
```ad-note
title:
If $\alpha_{1},\dots\alpha_{n} \in R$, then they form an integral basis iff $\mathrm{disc}(R) = \mathrm{disc(\alpha_{1},\dots,\alpha_{n})}$.

$\alpha_{1},\dots,\alpha_{n} \in R$ form an integral basis if $\mathrm{disc(\alpha_{1},\dots,\alpha_{n})}$ is square free.
```
###### Proof:
Both parts follow from Problem 3 in related problems below.

---
# Related Problems
1. Calculate $\mathrm{disc}(1,\omega, \dots ,\omega^{p-2})$ where $\omega = e ^{2\pi i/p}$. It comes out to be $\pm p ^{p-2}$.
   $f(x)(x-1) = x ^{p}-1$, differentiate to get $f'(x)(x-1) + f(x) = px ^{p-1}$, thus $f'(\omega) = p \frac{\omega^{p-1}}{\omega-1} = \frac{p}{\omega(\omega-1)}$.
   $N(f'(\omega)) = \frac{N(p)}{N(\omega)N(\omega-1)} = \frac{p ^{p-1}}{1 \cdot p} = p ^{p-2}$.
2. For $\mathrm{disc}(\omega)$ with $\omega = e ^{2\pi i/m}$, we can show that $\mathrm{disc}(\omega) \mid m ^{\varphi(m)}$.
   Let $f$ be min poly of $\omega$, then $x ^{m}-1 = f(x)g(x) \implies f'(x)g(x) + g(x)f'(x) = mx ^{m-1} \implies f'(\omega)g(\omega)=m \omega^{m-1} \implies m = \omega f'(\omega)g(\omega)$.
   Taking norms, $$
m ^{\varphi(m)} = N(f'(\omega))N(\omega g(\omega))
$$ establishing the result.
3. Let $G$ be a number ring of rank $n$, and $H$ be a subgroup of rank $n$. Then $|G /H|$ is finite, and $\mathrm{disc}(H) = |G /H|^{2} \mathrm{disc}(G)$.
   To show that $|G /H|$ is finite, look at proposition 3 of [[Free Group]].
   This means $G /H = \mathbb{Z}/d_{1}\mathbb{Z} \oplus \mathbb{Z} /d_{2}\mathbb{Z} \oplus \dots \oplus \mathbb{Z}/d_{n}\mathbb{Z}$. So, there is a basis $\beta_{1},\dots \beta_{n}$ for $G$ such that $d_{1}\beta_{1},\dots,d_{n}\beta_{n}$ is a basis for $H$. We can get the $\beta's$ by looking at the preimages of $(0,..0,1,0,\dots,0)$ type vectors in $G /H = \mathbb{Z}/d_{1}\mathbb{Z} \oplus \mathbb{Z} /d_{2}\mathbb{Z} \oplus \dots \oplus \mathbb{Z}/d_{n}\mathbb{Z}$.
   Note that now $\mathrm{disc}(H) = (d_{1}d_{2}\dots d_{n})^{2}\mathrm{disc}(G)$.

---
# References
[[Number Field]]
[[Trace and Norm]] 
[[Algebraic Integers]]
[[Free Group]]

