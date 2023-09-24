202306061206

Type : #Note
Tags : [[Number Theory]] [[Algebra]]

---
# Splitting of Primes in extensions
```ad-info
title: Discussion
We know of primes in $\mathbb{Z}$ which are not irreducible in latger extensions, for example $5 = (2+i)(2-i)$ in $\mathbb{Z}[i]$ and although 2,3 are primes in $\mathbb{Z}$, the ideals $(2)$ and $(3)$ split in $\mathbb{Z}[\sqrt[]{ -5 }]$.
$$
\begin{align}
(2) &= (2,1+\sqrt[]{ -5 })^{2} \\
(3) &= (3,1+\sqrt[]{ -5 })(3,1-\sqrt[]{ -5 })
\end{align}
$$
This phenomenon is called __splitting__. When we say that 3 splits as a product of two primes in $\mathbb{Z}[\sqrt[]{ -5 }]$, we really mean the prime ideal $(3)$ splits in $\mathbb{Z}[\sqrt[]{ -5 }]$.
We now consider the general problem of a given prime splitting in a given number ring.
```

From now on, let $K$ and $L$ be number fields with $K \subset L$, and $R = \overline{\mathbb{Z}} \cap K$ and $S = \overline{\mathbb{Z}} \cap L$.

### Theorem 1:
```ad-note
title:
Let $P$ be a prime ideal of $R$, and $Q$ a prime ideal of $S$. Then the following are equivalent:
1. $Q \mid PS$
2. $Q \supset PS$
3. $Q \supset P$
4. $Q \cap R = P$
5. $Q \cap K = P$
If any of the above conditions hold, $Q$ is said to __lie over__ $P$ or $P$ is said to __lie under__ $Q$.
```
###### Proof:
$(1) \implies (2) \implies (3)$ is easy.
$(3) \implies (4)$ We know that $Q \cap R \supset P$, and that $Q \cap R$ is a proper ideal of $R$ (otherwise $1 \in Q \cap R \subset Q \implies Q = S$), hence $P$ being a maximal ideal is equal to $Q \cap R$. 
$(4) \implies (5)$ $Q \cap K = Q \cap \overline{\mathbb{Z}} \cap K = Q \cap R = P$.
$(5) \implies (1)$, since $(5) \implies (4) \implies (3) \implies(2) \implies (1)$ (easy to check).

### Theorem 2:
```ad-note
title:
Every prime $Q$ of $S$ lies over a unique prime $P$ of $R$; every prime $P$ of $R$ lies under at least one prime $Q$ of $S$.
```
###### Proof:
Let $P = Q \cap R$, note that $P$ is a prime ideal of $R$, hence $Q$ lies over a prime ideal of $R$.
We just need to show that $Q \cap R \neq 0$, for this we take any element $\alpha \in Q$, take its norm $N ^{L}(\alpha) \in \mathbb{Z} \subset R$, we also know that $N ^{L}(\alpha) \in Q$, since the product of the conjugates of $\alpha$ other than $\alpha$ are contained in $S$.
Thus $N ^{L}(\alpha) \in Q \cap R \neq 0$.

If $Q$ lies over another prime $P_{1}$, $P_{1} = Q \cap R = P$ due to theorem 1, thus the prime $P$ is unique.

Now for the second part, given any prime $P$ of $R$, take $PS$ and look at its prime factorisation in $S$, $Q$ is any one of those prime factors. For this we need to show that $PS \neq S$.
For this, refer to lemma 2 of theorem 2 of [[Dedekind Domains]], and we get a $\gamma \in K - R$, such that $\gamma P \subset R \implies \gamma PS \subset RS = S$, thus if $1 \in PS$ then $\gamma \in PS$, this is a contradiction, therefore $PS \neq S$.

---

#### Definition:
The exponent of $Q$ in the prime decomposition of $PS$ is known as its __ramification index__, denoted by $e(Q | P)$.
###### Examples:
Let $R = \mathbb{Z}$ and $S = \mathbb{Z}[i]$, then $2S = (1-i)^{2}$, here $(1-i)$ is a prime which can be verified by looking at $|S /(1-i)| = 2$, and so $e((1-i)|2) = 2$. On the other hand, $e(Q | p) = 1$ for all $p \neq 2$ and $Q$ lying over $p$.

Now if $S = \mathbb{Z}[\omega]; \omega=e ^{2\pi i/m}; m = p ^{r}$, for some prime $p \in \mathbb{Z}$, then the principal ideal $(1-\omega)$ in $S$ is a prime lying over $p$, and $e((1-\omega)|p) = \phi(m)$.
$(1-\omega)$ is prime because $p = N(1-\omega)$, therefore $1-\omega \mid p$. Now $1-\omega \nmid j$ for all $1 \le j \le p$, since if it did, it would also divide $kp + 1$ for some $k$ (since we could multiply by $j$'s inverse modulo $p$.), and hence it would divide $1$, so it would be a unit and have norm $\pm 1$, that's a contradiction.
Thus, $0,1,\dots (p-1)$ lie in distinct congruence classes mod $(1-\omega)$.
We can show that any other element reduces to one of these classes. Thus $\mathbb{Z}[\omega]/(1-\omega) = \mathbb{F}_{p}$.

$e((1-\omega) | p) = \phi(m)$ because $p = u(1-\omega)^{\phi(m)}$ where $u$ is a unit.
This happens because $p = \prod_{k}(1-\omega^{k})$ where $k$ goes over all numbers $1 \le k \le m$ such that $(k,m) = 1$, and each $(1-\omega^{k}) = \frac{1-\omega^{k}}{1-\omega} \cdot (1-\omega)$. Here $\frac{1-\omega^{k}}{1-\omega}$ is a unit, since its reciprocal $\frac{1-\omega}{1-\omega^{k}} = \frac{1-\omega^{hk}}{1-\omega^{k}} = 1 + \omega ^{k} + \dots + \omega^{(h-1)k} \in \mathbb{Z}[\omega]$.
This gives $(p) = (1-\omega)^{\phi(m)}$

Whereas $e(Q | q) = 1$ whenever $q \neq p$ and $Q$ lies over $q$.

#### Definition:
We know that $R/P$ and $S /Q$ are fields. These are called the __residue fields__ modulo of $R$ and $S$ associated with $P$ and $Q$.
Moreover, we have an homomorphism $R \to S \to S /Q$ whose kernel is $R \cap Q = P$, thus there is an embedding $R /P \to S /Q$.
We know that these are finite fields and thus, $S /Q$ is a finite extension over $R /P$, let $f$ be the degree.
Then $f$ is called the __inertial degree__ of $Q$ over $P$, denoted by $f(Q|P)$.

###### Examples:
Let $R = \mathbb{Z}$ and $S = \mathbb{Z}[i]$, we have seen that $(1-i)$ lies above $2$. $S / (1-i)$ and $R /(2)$ both have order 2.
Hence, $R /P$ and $S /Q$ both are fields of order 2, and thus $f = 1$.
Whereas $3S$ is a prime in $S$, and $|S /3S| = 9$.
So $f(3S | 3) = 2$.

#### Note: $e$ and $f$ are multiplicative in towers.
If $P \subset Q \subset U$ are primes in the number rings $R \subset S \subset T$, then $$
\begin{align}
e(U|P) &= e(U|Q)e(Q|P) \\
f(U|P) &= f(U|Q)f(Q|P)
\end{align}
$$
We prove two theorems together, 
### Theorem 3:
```ad-note
title:
Let $n$ be the degree of $L$ over $K$, ($L,K,R,S$ as before) and let $Q_{1},\dots Q_r$ be the primes of $S$ lying over a prime $P$ of $R$. Let $e_{1},\dots e_{r}$ be the corresponding ramification indices. Let $f_{1},\dots ,f_{r}$ be the corresponding inertial degrees. Then $\sum_{i}e_{i}f_{i} = n$.
```

### Theorem 4:
```ad-note
title:
Let $R,S,K,L$ as before, and $n = [L:K]$. Let $\|I\|$ denote $|R/I|$ for an ideal $I$ of $R$.
1. For ideals $I,J \subset R$, $$
\|I\|\|J\| = \|IJ\|
$$
2. For an ideal $I \subset R$ and the ideal $IS \subset S$, $$
\|IS\| = \|I\| ^{n}
$$
1. Let $\alpha \in R \setminus \{ 0 \}$, for the principal ideal $(\alpha)$,$$
\|(\alpha)\| = |N ^{K}_{\mathbb{Q}}(\alpha) |
$$
```
###### Proof of 4.1:
We first prove this for coprime $I,J$ and then for prime powers, and the general result will follow.
If $I,J$ are coprime, then $I \cap J = IJ$ (in a number ring), and so by chinese remainder theorem, $$
R /I \times R/J \simeq R /IJ
$$
Giving us $\|I\|\|J\| = \|IJ\|$.

Now we will show that $|R /P ^{n}| = |R/P| ^{n}$.
We can show that $\|P\| = |P ^{k} / P ^{k+1} |$, and we will be done since $R /P ^{n} \simeq R /P \times P /P^{2} \times \dots P ^{n-1} /P ^{n}$
We will show an isomorphism between $$
R /P \to P ^{k} /P ^{k+1}
$$
Let $\alpha \in P ^{k} - P ^{k+1}$ be a non zero element, then there is an obvious isomorphism $$
R /P \to \alpha R /\alpha P
$$
Now there is a homomorphism $$
\alpha R \hookrightarrow P ^{k} \to P ^{k} /P ^{k+1}
$$
whose kernel is $\alpha R \cap P ^{k+1}$ and image is $(\alpha R+P ^{k})/ P ^{k+1}$.
Note that $\alpha R + P ^{k} = \mathrm{gcd}(\alpha R,P ^{k}) = P ^{k}$, and $\alpha R \cap P ^{k+1} = \mathrm{lcm}(\alpha R,P ^{k+1}) = \alpha P$.
Giving us $$
\alpha R/\alpha P \simeq P ^{k} /P ^{k+1}
$$
as needed.

###### Proof 3 (Special case):
For the case when $K = \mathbb{Q}$.
Then $P = p\mathbb{Z}$ for some prime $p$. We have $$
pS = \prod_{i=1}^{r}Q_{i}^{e_{i}}
$$
hence $$
\begin{align} 
\|pS\| = \prod_{i=1}^{r} \|Q_{i}\| ^{e_{i}} = \prod_{i=1}^{r}(p ^{f_{i}})^{e_{i}} 
\end{align}
$$
On the other hand, we know $\|pS\| = p ^{n}$, and we are done.

###### Proof 4.2:
See that $S /PS$ is a ring containing $R /P$ and hence is a vector space over it.

Let $\alpha_{1},\dots,\alpha_{n+1} \in S$, we show that the corresponding elements in $S /PS$ are linearly dependent.
Since the $\alpha_{i}$'s are linearly dependent over $K$, they are dependent over $R$. Thus there are $\beta_{i} \in P, \ \forall i \in [n+1]$ s.t. $$
\sum\alpha_{i}\beta_{i} = 0
$$
we want to show that not all of the $\beta_{i}$'s are in $P$.

By lemma 3 of [[Dedekind Domains]] applied to $A = P$ and $B = (\alpha_{1},\dots,\alpha_{n+1})$, we get that there is a $\gamma \in K$ such that $\gamma B \subset R$, but $\gamma B \nsubseteq P$, multiplying the above equation by $\gamma$, we get the required fact.

Now we need to show that the dimension is infact equal to $n$.
Let $P \cap \mathbb{Z} = p\mathbb{Z}$ and consider all primes $P_{i}$ of $R$ lying above $p$. We know $S /P_{i}S$ is a vector space over $R /P_{i}$ with dimension $n_{i}$, we will show that each $n_{i} = n$.
Set $e_{i} = e(P_{i}|p)$ and $f_{i} = f(P_{i}|p)$.
Then we know by the special case of theorem 3 proved above, $$
\sum e_{i}f_{i} = m
$$
where $m = [K : \mathbb{Q}]$.
We have $$
\begin{align} \\
pS &= \prod_{i}P_{i}^{e_{i}}S = \prod_{i}(P_{i}S)^{e_{i}}  \\
\implies \|pS\| &= \prod_{i}\|P_{i}S\| ^{e_{i}} =  \prod_{i} \|P_{i}\| ^{n_{i}e_{i}} = \prod_{i}p ^{f_{i}n_{i}e_{i}}
\end{align}
$$
But we also know $\|pS\| = p ^{mn}$.
This gives $$
\begin{align}
mn &= \sum_{i}f_{i}n_{i}e_{i}  \\
\implies \sum_{i}n_{i}f_{i}e_{i} = \sum_{i}e_{i}f_{i}n
\end{align}
$$
And since $n_{i} \le n$, it is infact equal to $n$.

###### Proof 3 (General case):
We have $PS = \prod_{i}Q_{i}^{e_{i}}$.
$$
\begin{align}
\|P\| ^{n} = \|PS\| &= \prod_{i}\|Q_{i}\| ^{e_{i}}  \\ \\
&= \prod_{i}\|P\| ^{f_{i}e_{i}} \\
\implies n &= \sum_{i} f_{i}e_{i}
\end{align}
$$
###### Proof 4.3:
Let $M$ be a normal extension of $K$, and let $T = \overline{\mathbb{Z}} \cap M$.
For each embedding $\sigma$ of $K$ in $\mathbb{C}$, we have $$
\|\alpha T\| = \|\sigma(\alpha)T\|
$$
This is true because, we can extend $\sigma$ to $M$, and note that $\sigma (T) = \sigma(K \cap \overline{\mathbb{Z}}) = \sigma(K) \cap \sigma(\overline{\mathbb{Z}}) = K \cap \overline{\mathbb{Z}} = T$.

Now $T /\alpha T \to \sigma T /\sigma(\alpha T) = T /\sigma(\alpha)T$ is an isomorphism. Where the first arrow is the map that takes $x + \alpha T$ to $\sigma(x) + \sigma(\alpha)T$.

Now let $N = N_{\mathbb{Q}}^{K}(\alpha)$ and let $m = [M : K]$

$$
\begin{align}
\|NT\| &= \prod_{\sigma}\|\sigma(\alpha)T\| \\
\implies |N| ^{mn} &= \prod_{\sigma} \|\alpha T\| \\
&= \|\alpha T\| ^{n} \\
&= \|(\alpha R)\| ^{mn} \\
\implies |N| &= \|(\alpha)\|
\end{align}
$$
#### Applications:
1. $(1-\omega)$ is a prime ideal in $\mathbb{Z}[\omega]$, where $\omega = e ^{2\pi i/p ^{r}}$ We know that $p\mathbb{Z}[\omega] = (1-\omega)^{n}$ where $n = \phi(p ^{r})$, since $n$ is the degree of $\mathbb{Q}(\omega)$ over $\mathbb{Q}$, any futher splitting of $(1-\omega)$ would violate the above theorem.
2. This can also be seen by observing $\|(1-\omega)\| ^{n} = \|(1-\omega) ^{n}\| = \|p\mathbb{Z}[\omega]\| = p ^{n} \implies \|(1-\omega)\| = p$, now theorem 4.1 gives that $(1-\omega)$ is a prime ideal.

---
### Theorem 5:
```ad-note
title:
If $L$ is a normal extension of $K$ and $P$ is a prime in $R$, the galois group $\mathrm{Gal}(L /K)$ permutes the primes lying over $P$ and it does so transitively.
```
###### Proof:
Fix a prime $Q$ lying over $P$, and $\sigma \in \mathrm{Gal}(L /K)$, then $\sigma(Q)$ is another prime ideal over $P$, since $\sigma(Q) \cap K = Q \cap K = P$.
Now let $Q'$ be a prime over $P$ such that $\sigma(Q) \neq Q'$ for all $\sigma \in G$.
Now choose an element $x \in S$ such that $$
\begin{align}
x \equiv 1 \ (\mathrm{mo d}\ \sigma(Q)) \\
x \equiv 0 \ (\mathrm{m od}\ Q')
\end{align}
$$
this is possible by CRT.

Now $N ^{L}_{K}(x) \in R \cap Q' = P$.
We have $x \notin \sigma(Q) \implies \sigma^{-1}(x) \notin Q$ for all $\sigma \in \mathrm{Gal}(L /K)$.
But this means $N ^{L}_{K}(x) = \prod_{\sigma} \sigma^{-1}(x) \notin Q$, this is a contradiction since $N_{K}^{L}(x) \in P \subset Q$.

### Corollary:
```ad-note
title:
If $L$ is normal over $K$ and $Q$ and $Q'$ are two primes above $P$, then $e(Q|P) = e(Q'|P)$ and $f(Q|P) = f(Q'|P)$.
```
###### Proof:
$e(Q|P) = e(Q'|P)$ follows from unique factorisation.
For the second part, note the chain of isomorphisms:$$
S /Q \to \sigma S /\sigma Q \to S /\sigma Q
$$
---
### Definition:
```ad-note
title:
A prime $P$ of $R$ is __ramified__ in $S$ (or in $L$) if $e(Q|P) >1$ for some prime $Q$ of $S$ lying over $P$.
```

### Theorem 6:
```ad-note
title:
Let $p$ be a prime in $\mathbb{Z}$, and suppose $p$ is ramified in a number ring $R$. Then $p \mid \mathrm{disc}(R)$.
```
###### Proof:
Let $P$ be a prime in $R$ lying over $p$, such that $e(P|p) > 1$.
Let $pR = PI$, with $I$ divisible by all primes of $R$ lying over $p$.

Let $\sigma_{1},\dots \sigma_{n}$ denote the embeddings of $K$ into $\mathbb{C}$, and extend these to automorphisms of an extension $L$ of $K$, which is normal over $\mathbb{Q}$.

Let $\alpha_{1},\dots\alpha_{n}$ be an integral basis of $R$. The idea is to find a collection of linearly independent elements whose discriminant is divisible by $p$ and s.t. the subgroup $H$ generated by them satisfies $p \nmid |R /H|$. (Look at [[Discriminant of an n-tuple]], related problems, Problem 3).

Let $\alpha \in I - pR$, $\alpha = m_{1}\alpha_{1} + \dots + m_{n}\alpha_{n}$, since $\alpha \notin pR$, one of the $m_{i}$'s is not divisible by $p$, WLOG let it be $m_{1}$.
Then $\mathrm{disc}(\alpha,\alpha_{2},\dots\alpha_{n}) = m_{1}^{2}\mathrm{disc}(\alpha_{1},\dots,\alpha_{n})$.

Now note that $\alpha$ is in every prime of $R$ lying over $p$, and hence in every prime of $S$ lying over $p$.
Fix a prime $Q$ of $S$ lying over $P$, then $\sigma^{-1}(Q)$ is another prime lying over $p$, and so $\alpha \in \sigma^{-1}(Q)$
This means $\sigma_{i}(\alpha) \in Q$ for all $i = 1,2,\dots n$ implying $\mathrm{disc}(\alpha,\alpha_{2},\dots,\alpha_{n}) \in Q \subset p\mathbb{Z}$.

Thus we are done.

### Corollary 1:
```ad-note
title:
Let $\alpha \in R$, $K = \mathbb{Q}[\alpha]$ and let $f$ be any monic poly over $\mathbb{Z}$ s.t. $f(\alpha) = 0$. If $p$ is a prime such that $p \nmid N ^{K}(f'(\alpha))$, then $p$ is unramified in $K$.
```
###### Proof:
Note that $m_{\alpha}'(\alpha) \mid f'(\alpha)$ where $m_{\alpha}(x)$ is the monic minimal poly of $\alpha$ over $\mathbb{Q}$. Thus, $N ^{K}(m_{\alpha}'(\alpha)) \mid N ^{K}(f'(\alpha)) \implies \mathrm{disc}(\alpha) \mid N ^{K}(f'(\alpha))$.
So if $p \nmid N ^{K}(f'(\alpha))$, then $p \nmid \mathrm{disc}(\alpha)$ hence $p$ is unramified.

### Corollary 2:
```ad-note
title:
Only finitely many primes of $\mathbb{Z}$ are ramified in a number ring $R$.
```
###### Proof:
Since there are only finitely many prime divisors of $\mathrm{disc}(R)$.

### Corollary 3:
```ad-note
title:
Let $R$ and $S$ be number rings, $R \subset S$, then only finitely many primes of $R$ are ramified in $S$.
```
###### Proof:
If $P$ is a prime ramified in $S$, then $P \cap \mathbb{Z} = p\mathbb{Z}$ is ramified in $S$. But there are only finitely many such $p's$, and any such $p$ has only finitely many primes lying over it in $R$, hence only finitely many primes of $R$ ramify in $S$.

---
# Splitting primes in Cyclotomic extensions
Let $\omega = e ^{2\pi i/m}$ and fix a prime $p \in \mathbb{Z}$. Since $\mathbb{Q}(\omega)$ is a normal extension of $\mathbb{Q}$, the corollary to theorem 5 shows that $$
p\mathbb{Z}[\omega] = (Q_{1}\dots Q_{r})^{e}
$$
where $Q_{i}'s$ are distinct primes in $\mathbb{Z}[\omega]$ with same inertial degrees and we have $ref = \phi(m)$.

### Theorem 7:
```ad-note
title:
Write $m = p ^{k}n$ with $p \nmid n$. Then we have $e = \phi(p ^{k})$ and $f =$ the multiplicative order of $p$ mod $n$. 
```
###### Proof:
Let $\alpha = \omega^{p ^{k}}$ and $\beta = \omega^{n}$.
Then $\alpha$ is an $n ^{th}$ root of unity and $\beta$ is a $(p ^{k})^{th}$ root of unity.
We will first see how $p$ splits in $\mathbb{Q}(\alpha),\mathbb{Q}(\beta)$ and then combine our knowledge to get the splitting behaviour in $\mathbb{Q}(\omega)$.

When $p \nmid m$, then $k = 0$ and $n = m$, thus $\alpha = \omega$ and $\beta = 1$.
When $p \mid m$, we consider how $p$ splits in $\mathbb{Q}(\beta)$.
We know that $p = u(1-\beta)^{\phi(p ^{k})}$, and thus $p\mathbb{Z}[\beta] = (1-\beta)^{\phi(p ^{k})}$, and since $\phi(p ^{k}) = [\mathbb{Q}(\beta) :\mathbb{Q}]$, we get that $(1-\beta)$ is a prime ideal in $\mathbb{Z}[\omega]$ (by theorem 3).

Now let's see how it splits in $\mathbb{Q}(\alpha)$.
Since $p \nmid n$, $p \nmid \mathrm{disc}(\mathbb{Z}[\alpha]) \mid n ^{\phi(n)}$ (refer to [[Discriminant of an n-tuple]]), hence $p$ is unramified in $\mathbb{Z}[\alpha]$ and so $$
p\mathbb{Z}[\alpha] = P_{1}P_{2}\dots P_{r}
$$
where $P_{i}'s$ are distinct primes each with the same inertial degree $f$, and $rf = \phi(n)$.

#### Claim:
```ad-note
title:
$f$ is the order of $p$ mod $n$.
```
###### Proof:
Note that the galois group of $\mathbb{Q}(\alpha)$ over $\mathbb{Q}$ is the multiplicative group $\mathbb{Z}_{n}^{*}$. Take the automorphism $\sigma \in \mathrm{Gal}(\mathbb{Q}(\alpha)/\mathbb{Q})$ corresponding to $\bar{p} \in \mathbb{Z}_{n}^{*}$. The order of $\sigma$ in $\mathrm{Gal}(\mathbb{Q}(\alpha)  / \mathbb{Q})$ is the same as the order of $p$ mod $n$.
Now fix a $P_{i} = P$, then $\mathbb{Z}[\alpha] /P$ has degree $f$ over $\mathbb{Z}_{p}$ and hence the galois group $\mathrm{Gal}((\mathbb{Z}[\alpha] /P) / \mathbb{Z}_{p})$ is a cyclic group (since finite fields) of order $f$. Let $\tau$ be the generator of this group ($\tau$ is the map that takes an element to its $p ^{th}$ power).

We need to show that $\sigma$ and $\tau$ have the same order.
Now let $\sigma^{a} = 1$,
$$
\begin{align}
\sigma^{a} = 1 &\iff \alpha^{p ^{a}} = \alpha  \\
&\iff p ^{a} = 1 \ (\mathrm{mo d}\ n) \\
\end{align}
$$
On the other hand, $$
\begin{align}
\tau^{a} = 1 &\iff \alpha^{p ^{a}} = \alpha \ (\mathrm{mo d} \ P) \\
\end{align}
$$
We must show $p ^{a} = 1 \ (\mathrm{mo d}\ n)$. Let $p ^{a} = b \ (\mathrm{mo d}\ n)$, then $\alpha^{b} = \alpha \ (\mathrm{mo d}\ P) \implies \alpha^{b-1} = 1 \ (\mathrm{mo d}\ P)$.
Now we know $$
(1-\alpha)(1-\alpha^{2})\dots(1-\alpha^{n-1}) = n
$$
If $b \neq 1$, then $n \in P$ from the above equation, this is impossible since $p \in P$ and $(n,p) = 1$.
Thus $b = 1$.

Finally, we can put together $\mathbb{Z}[\alpha]$ and $\mathbb{Z}[\beta]$.
Fix primes $Q_{1},\dots,Q_{r}$ of $\mathbb{Z}[\omega]$ lying above $P_{1},P_{2},\dots P_{r}$ respectively.
Since all $Q_{i}$ lie over $p$, they must lie over $(1-\beta)$ since it's the only prime in $\mathbb{Z}[\beta]$ lying over $p$.
Now $e(Q_{i} | p) \ge e((1-\beta)|p) = \phi(p ^{k})$
and $f(Q_{i}|p) \ge f(P_{i}|p) = f$.
Thus, $\sum_{i}e(Q_{i}|p)f(Q_{i}|p) \ge r\phi(p ^{k})f = \phi(p ^{k}) \phi(n) = \phi(m)$.
Thus, $e(Q_{i}|p) = \phi(p ^{k})$ and $f(Q_{i}|p) = f$ and the $Q_{i}'s$ are the only primes of $\mathbb{Z}[\omega]$ lying over $p$.

### Corollary:
```ad-note
title:
If $p \nmid m$, then $p$ splits into $\phi(m) /f$ distinct prime ideals in $\mathbb{Z}[\omega]$, where $f$ is the order of the prime $p$ mod $n$.
```

---
# Method to factorise a prime ideal in an extension
### Theorem 8:
```ad-note
title:
Let $R,S,L,K$ as before, and let $n = [L:K]$. Fix an element $\alpha \in S$ of degree $n$ over $K$, so that $L = K[\alpha]$ ([[Primitive Element Theorem]]).
In general, $R[\alpha]$ is a subgroup of $S$, and the factor group $S /R[\alpha]$ is finite (Problem 3 of related problems, [[Discriminant of an n-tuple]], and the fact that both are free abelian groups of rank $mn$).
Fix a prime $P$ of $R$.
Now let $g$ be the monic irreducible poly for $\alpha$ over $K$ (this has coefficients in $R$).
Now consider $\overline{g} \in (R /P)[x]$, it factors uniquely in $(R /P)[x]$ 
$$
g = \overline{g_{1}}^{e_{1}}\dots \overline{g_{r}}^{e_{r}}
$$
where the $g_{i}$ are monic irreducible polynomials over $R$ such that $\overline{g_{i}}$ are all distinct. 

Now assume that $p \nmid |S /R[\alpha]|$, where $p$ is a prime of $\mathbb{Z}$ lying under $P$. Then the prime decomposition of $PS$ is given by 
$$
Q_{1}^{e_{1}}\dots Q_{r}^{e_{r}}
$$
where $Q_{i} = (P,g_{i}(\alpha)) = PS + (g_{i}(\alpha))$.
Also, $f(Q_{i}|P) = \mathrm{deg}(g_{i})$.
```
###### Proof:
Let $f_{i} := deg(g_{i})$.
We need to show that: 
1) $PS \supset Q_{1}^{e_{1}}\dots Q_{r} ^{e_{r}}$
2) $Q_{i}+  Q_{j} = S$ for all $i\neq j$.
3) For all $i$, either $S = Q_{i}$ or $S /Q_{i}$ is a field of order $|R /P| ^{f_{i}}$ 

Once we show these, we can conclude as follows, 
(3) implies $f_{i} = f(Q_{i}|P)$
(1) implies that $PS = \prod_{j}Q_{j}^{k_{j}}$ with $k_{j} \le e_{j}$, giving $\sum_{j} f(Q_{j}|P)k_{j} = mn \le \sum_{j}f_{j}e_{j} = deg(g) = mn$
This gives $k_{j} = e_{j}$ and that all $Q_{i}'s$ are primes and we are done.

1. This is easy,
$$
\begin{align}
Q_{1}^{e_{1}}\dots Q_{r} ^{e_{r}} &= \prod_{i}(PS+(g_{i}(\alpha))) ^{e_{i}} \\ \\
&\subset PS + \left(\prod_{i}g_{i}^{e_{i}}(\alpha)\right) \\
&= PS + (0) = PS
\end{align}
$$
2. $Q_{i}+Q_{j} = PS + (g_{i}(\alpha)) + (g_{j}(\alpha))$.
   Since $\overline{g_{i}}$ and $\overline{g_{j}}$ are irreducibles in $(R /P)[x]$, there are two polys $\overline{u},\overline{v} \in (R /P)[x]$ such that $$
\begin{align}
&\overline{ug_{i} + vg_{j}} = \overline{1}  \\
&\implies ug_{i} +vg_{j} - 1 \in P [x] \\
&\implies u(\alpha)g_{i}(\alpha) + v(\alpha)g_{j}(\alpha) - 1 \in P[\alpha] \subset R[\alpha] \subset S \\
&\implies  u(\alpha)g_{i}(\alpha) + v(\alpha)g_{j}(\alpha) - 1 \in PS \\
&\implies 1 \in Q_{i} + Q_{j} = PS + (g_{i}(\alpha)) + (g_{j}(\alpha))
\end{align}
$$
3. Let $F_{i} := (R /P)[x] /(\overline{g_{i}})$, this is a field of size $|R /P| ^{f_{i}}$. We show that this is isomorphic to $S /Q_{i}$.
 Take the homomorphism $R[x] \to F_{i}$ defined in the obvious way, modding by $P$, then by $(\overline{g_{i}})$. This is onto, with kernel $(P,g_{i})$.
 Now map $R[x] \to R[\alpha] \subset S$, this induces a homomorphism $R[x] \to S /Q_{i}$. The kernel for this contains $P$ and $g_{i}$, and hence it contains $(P,g_{i})$ which is a maximal ideal as seen above. Thus the kernel is either $(P,g_{i})$ or $S$. Moreover, this is onto, to show this we need to show that $R[\alpha] + Q_{i} = S$.
 
 We know that $p \in P \subset Q_{i}$, hence $pS \subset Q_{i}$. Thus, $S = R[\alpha] + pS$, since $|S /(R[\alpha] + pS)|$ is a common divisor of $|S /R[\alpha]|$ and $|S /pS| = p ^{mn}$, which is $1$ (prove this using 3rd isomorphism theorem).
 
 Thus, we get that $S /Q_{i}$ is either $R[x] /(P,g_{i})$ or is just zero according to the two choices of the kernel.
 This gives the result.

---
# Splitting primes in quadratic extensions
Let $p$ be a prime in $\mathbb{Z}$, then there are three possibilities according to theorem 3:
$$
pR = \begin{cases}
P^{2}, & f(P|p) = 1 \\
P, & f(P|p) = 2 \\
P_{1}P_{2}, & f(P_{1}|p) = f(P_{2}|p) = 1
\end{cases}
$$
### Theorem 9:
```ad-note
title:
With notation as above, we have:
if $p \mid m$, then 
$$
pR = (p,\sqrt[]{ m })^{2}
$$
If $m$ is odd, then 
$$
2R = \begin{cases}
(2,1 + \sqrt[]{ m })^{2} & \text{if } m \equiv 3 \ (\mathrm{mo d}\ 4) \\
\left( 2, \frac{1 + \sqrt[]{ m }}{2} \right) \left( 2, \frac{1-\sqrt[]{ m }}{2} \right)  & \text{if } m \equiv 1 \ (\mathrm{mo d}\ 8) \\
\mathrm{prime} & \text{if } m \equiv 5 \ (\mathrm{mo d}\ 8)
\end{cases}
$$
If $p$ is odd, $p \nmid m$ then 
$$
pR = \begin{cases}
(p,n + \sqrt[]{ m })(p,n-\sqrt[]{ m }) & \text{if } m\equiv n^{2} \ (\mathrm{mo d}\ p) \\
\mathrm{prime} & \text{if $m$ is not a square mod $p$}
\end{cases}
$$
```
###### Proof:
Use theorem 8.
Let $\alpha = \sqrt[]{ m }$.
Now $R \supset = \mathbb{Z}[\alpha] = \mathbb{Z}[\sqrt[]{ m }]$.
This is a proper inclusion iff $m \equiv 1 \ (\mathrm{mo d}\ 4)$.
Note that in the case when $m$ is 1 mod 4, we have $|S /\mathbb{Z}[\sqrt[]{ m }]| = 2$.
So, for $p = 2$ and $m = 1$ mod 4, we will have to use $\alpha = \frac{1+\sqrt[]{ m }}{2}$.

For the first case, 
we have $g(x) = x^{2}-m$, $\overline{g}(x) = x^{2} - \overline{m}$.
If $p \mid m$, then $\overline{g}(x) = x^{2} \implies pR = Q^{2}$ where $Q = pR + (\sqrt[]{ m }) = (p,\sqrt[]{ m })$.

If $p \nmid m$, then $\overline{g}$ is irreducible if $m$ is not a square mod $p$, and reducible if $m$ is a square mod $p$.
$\overline{g}(x) = (x-n)(x+n) \implies pR = (p,\sqrt[]{ m } + n)(p,n-\sqrt[]{ m })$.

This takes care of all cases except when $p = 2, m = 1$ mod 4.
For that, take $\alpha = \frac{1 + \sqrt[]{ m }}{2}$.
Then $g(x) = x^{2} - x + \frac{1-m}{4}$, taken mod 2, $\overline{g}(x) = x^{2}+x+\frac{1-m}{4}$.
If $m = 1$ mod 8, then $\overline{g}(x) = x^{2} + x \implies pR =(2,\alpha)(2,\alpha+1)$.
If $m = 5$ mod 8 then $\overline{g}(x)$ is irreducible and $pR$ is prime.


---
# References
[[Number Rings]]
[[Dedekind Domains]]
[[Trace and Norm]]
[[Normal Extensions]]
[[Galois Correspondence]]
[[Discriminant of an n-tuple]]
[[Primitive Element Theorem]]