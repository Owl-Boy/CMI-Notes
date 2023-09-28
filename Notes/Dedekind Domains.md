202306050906

Type : #Note
Tags : [[Number Theory]] [[Algebra]]

---
# Dedekind Domains
```ad-note
title:
A **Dedekind Domain** is an integral domain $R$ such that 
1. Every ideal is finitely generated.
2. Every non zero prime ideal is maximal.
3. $R$ is _integrally closed_ in its field of fractions $$
K = \left\{  \frac{\alpha}{\beta} : \alpha,\beta \in R, \beta \neq 0  \right\}
$$
```
(3) means that if $\frac{\alpha}{\beta} \in K$ is a root of a monic polynomial with coefficients in $R$, then $\frac{\alpha}{\beta} \in R$.
(1) is equivalent to : 
(1') Every increasing sequence of ideals is eventually constant: $$
I_{1} \subset I_{2} \subset \dots 
$$
implies that all $I_{n}$ are equal for sufficiently large $n$.
(1'') Every non empty set $S$ of ideals has a (not necessarily unique) maximal element.

A ring satisfying the equivalent conditions $(1),(1'),(1'')$ is called a **Noetherian Ring**.

### Theorem 1:
```ad-note
title:
Every number ring is a Dedekind Domain.
```
###### Proof:
See [[Number Rings]] theorem 5.

### Theorem 2:
```ad-note
title:
Let $I$ be any ideal of a dedekind domain $R$, then there is an ideal $J$ such that $IJ$ is principal.
```
Let $\alpha$ be any nonzero member of $I$, then define $J := \{ \beta \in R  : \beta I \subset (\alpha)\}$, note that $\alpha \in J$ and that it is an ideal.
Thus $IJ \subset (\alpha)$. We will show that equality holds.

### Lemma 1:
```ad-note
title:
In a dedekind domain, every ideal contains a product of prime ideals.
```
###### Proof:
Suppose not, there consider the non empty set of ideals that do not contain a product of prime ideals, call it $S$. This has a maximal element by condition (1'') of [[Dedekind Domains]], call it $M$.
Then $M$ can't be prime hence there are $r,s \in R - M$ such that $rs \in M$.
$M + (r)$ and $M+(s)$ are bigger than $M$ hence are not contained in $S$, hence contain a product of prime ideals. 
But then so does $(M+(r))(M+(s)) \subset M$, this is a contradiction.

### Lemma 2:
```ad-note
title:
Let $A$ be a proper ideal in a dedekind domain $R$ with field of fractions $K$. Then there is an element $\gamma \in K - R$ such that $\gamma A \subset R$.
```
###### Proof:
Let $\alpha \in A$ be any non zero element, then $(\alpha)$ contains a product of prime ideals.
Let $(\alpha) \supset P_{1}P_{2}\dots P_{r}$ where $P_{i}$'s are prime ideals and $r$ is the least possible.
Now $A$ is contained in a maximal ideal, call it $P$, it is also prime.
$P \supset A \supset (\alpha) \supset P_{1}P_{2}\dots P_{r}$.
Now if none of the prime ideals $P_{i}$, are contained in $P$, then there are elements $a_{i} \in P_{i}-P$ such that $\prod_{i}a_{i} \in P$, this is a contradiction to the fact that $P$ is prime.
Thus WLOG, $P \supset P_{1}$, and since both are maximal, $P = P_{1}$.

Now $\exists \beta \in P_{2}P_{3}\dots P_{r} - (\alpha)$ (since $(\alpha)$ doesn't contain the product $P_{2}P_{3}\dots P_{r}$).
Let $\gamma = \frac{\beta}{\alpha}$, then $\gamma A \subset \gamma P \subset \frac{1}{\alpha}PP_{2}\dots P_{r} \subset \frac{1}{\alpha}(\alpha)$.

Returning to the proof of the theorem, let $A = \frac{1}{\alpha}IJ$, we want to show $A = R$. 
Suppose not, then $A$ is a proper ideal, and so there exists a $\gamma \in K - R$, such that $\gamma A\subset R$.
This implies $\gamma IJ \subset (\alpha) \implies \gamma J \subset J$.
$J$ is finitely generated, let $\alpha_{1},\dots\alpha_{m}$ be the generators, 
then $$
\begin{pmatrix}
\gamma\alpha_{1}  \\
\vdots \\
\gamma\alpha_{m}
\end{pmatrix}
= M \begin{pmatrix}
\alpha_{1} \\
\vdots \\
\alpha_{m}
\end{pmatrix}
$$
where $M \in M_{m}(R)$, this gives $\det(M-\gamma I) = 0$, hence $\gamma$ satisfies a monic poly over $R$, hence $\gamma \in R$. This is a contradiction.

### Corollary 1:
```ad-note
title:
The ideal classes in a dedekind domain form a group.
```
#### NOTE:
We can put an equivalence relation on the set of ideals of a commutative ring $R$ as follows:
$I \sim J$ iff $\exists \ \alpha,\beta \in R$ s.t. $\alpha I = \beta J$.
We can multiply ideal classes by taking representatives from each class.
This multiplication is associative and commutative since the ring is commutative.
The identity is the class of all principal ideals.
This forms a group in the case of dedekind domains since we have inverses.

### Corollary 2 (Cancellation Law):
```ad-note
title:
If $A,B,C$ are ideals in a dedekind domain, and $AB = AC$, then $B = C$.
```
###### Proof:
There is an ideal $I$ such that $IA = (\alpha)$ for some $\alpha \in R$.
Thus, $\alpha B = \alpha C$ from which we get $B = C$.

### Corollary 3:
```ad-note
title:
If $A,B$ are ideals in a dedekind domain $R$, then $A \mid B$ iff $A \supset B$.
```
###### Proof:
If $A \mid B$, then $B = AC \subset AR  = A$.
If $B \subset A$, then there is an ideal $J$ such that $AJ = (\alpha)$.
Then $B = A(\frac{1}{\alpha}JB)$, and note that $\frac{1}{\alpha}JB$ is an ideal in $R$.

### Theorem 3:
```ad-note
title:
Every ideal in a dedekind domain $R$ is uniquely representable as a product of prime ideals.
```
###### Proof:
Consider the set of all proper ideal not representable in such a form, call it $S$. Now $S$ contains a maximal (in $S$) element $M$.
$M$ is not a maximal ideal, hence it is properly contained in some maximal ideal $P$. Thus by corollary 3, $M = PI$ for some $I$.
Now $I \supset M$ again by corollary 3 above, this containment is strict since otherwise $I = M \implies PI = PM \implies RM = PM \implies R = P$, contradiction.
Thus, $M = PI$, both of which do not belong to $S$, thus $M$ doesn't belong to $S$, thus $S$ is empty.

Now let $I = P_{1}P_{2}\dots P_{n} = Q_{1}\dots Q_{m}$ be two representations of an ideal $I$ as a product of prime ideals.
Then $P_{1} \supset Q_{1}\dots Q_{m}$, then it contains one of them, WLOG $P_{1} \supset Q_{1} \implies P_{1} = Q_{1} \implies P_{2}\dots P_{n} = Q_{2}\dots Q_{m}$.
Continuing this way, we get $P_{i} = Q_{i}$ and $n = m$.

---
### Definition
```ad-note
title:
We can define the $\mathrm{gcd}$ and $\mathrm{lcm}$ of ideals in a DD with the help of their prime decomposition in the obvious way. We also have $$
\begin{align}
\mathrm{gcd}(I,J) = I + J \\
\mathrm{lcm}(I,J) = I \cap J
\end{align}
$$
```

### Theorem 4:
```ad-note
title:
Let $I$ be an ideal in a DD $R$, and let $\alpha$ be a non zero element of $I$. Then there exists $\beta \in I$ such that $(\alpha,\beta) = I$.
```
###### Proof:
It is enough to construct a $\beta \in R$ such that $I = \mathrm{gcd}((\alpha),(\beta))$, then $\beta \in I$ automatically.

Let $(\alpha) = P_{1}^{n_{1}}\dots P_{r}^{n_{r}}$ where $P_{i}$ are prime ideals. Let $Q_{1},\dots,Q_{m}$ denote the other prime ideals dividing $(\alpha)$.
Then we need to construct $\beta$ such that $Q_{j} \nmid (\beta)$ and $P_{i}^{n_{i}}$ is the exact power of $P_{i}$ that divides $(\beta)$.
This can be done by Chinese remainder theorem.
Choose $\beta_{i} \in P_{i}^{n_{i}} - P_{i}^{n_{i}+1}$, and solve the system $$
\begin{align}
\beta \equiv \beta_{i} \ (\mathrm{mod }\ P_{i} ^{n_{i}+1}) \\
\beta \equiv 1 \ (\mathrm{mo d} \ Q_{i})
\end{align}
$$
noting that each of the ideals $P_{i}^{n_{i}+1}$ and $Q_{j}$ are coprime to each other.

### Theorem 5:
```ad-note
title:
A DD is a UFD iff it is a PID.
```
###### Proof:
We know $PID \implies UFD$.
Suppose the DD is a UFD, then take any ideal $I$ in $R$. It divides some principal ideal $(\alpha)$ by theorem 2.
$\alpha = p_{1}p_{2}\dots p_{n}$ is a product of primes in $R$, hence $(\alpha) = (p_{1})(p_{2})\dots(p_{n})$.
$I \mid (p_{1})\dots(p_{n})$, now by uniqueness of prime factorisation of ideals, $I$ is a product of principal ideals and hence is principal.

### Lemma 3:
```ad-note
title:
Let $A$ and $B$ be nonzero ideals in a DD $R$ with $B \subset A$ and $A \neq R$.
Then there exists $\gamma \in K$ such that $\gamma B \subset R$ but $\gamma B \nsubseteq A$.
```
###### Proof:
We know there is an ideal $C$ such that $BC = (\alpha)$ for some $\alpha$.
Then $BC \nsubseteq \alpha A$; fix any $\beta \in C$ such that $B \beta \nsubseteq \alpha A$, then $\gamma = \frac{\beta}{\alpha}$ works.




---
# References
[[Number Rings]]
[[Principal Ideal Domain]]
