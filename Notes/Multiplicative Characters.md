202305261505

Type : #Note
Tags : [[Number Theory]] [[Algebra]]

---
# Multiplicative Characters
```ad-note
title:
A multiplicative character on $\mathbb{F}_p$ is a group homomorphism $\chi$ from $\mathbb{F}_p^*$ to the non zero complex numbers.
```
- The [[Legendre Symbol]] $(a /p)$ is such an example.
- Another example is the trivial character $\varepsilon$ which takes everything to 1.

Often we extend the domain of definition of the character to include $0 \in \mathbb{F}_{p}$, and we define $\chi(0) = 0$ if $\chi \neq \varepsilon$ and $\varepsilon(0) = 1$.

### Proposition 1:
```ad-note
title:
Let $\chi$ be a multiplicative character and $a \in \mathbb{F}_{p}^{*}$. Then 
1. $\chi(1) = 1$
2. $\chi(a)$ is a $(p-1)$th root of unity.
3. $\chi(a ^{-1}) = \chi(a) ^{-1} = \overline{\chi (a)}$
```

### Proposition 2:
```ad-note
title:
Let $\chi$ be a multiplicative character. If $\chi \neq \varepsilon$, then $\sum_{t} \chi(t) = 0$ where the sum is over all $t \in \mathbb{F}_{p}$. If $\chi = \varepsilon$, the value of the sum is p.
```
###### Proof:
For $\chi \neq \varepsilon$, there is an $a \in \mathbb{F}_{p}^{*}$ such that $\chi(a) \neq 1$. Now let the sum in question be equal to $T$. Then $$
\chi(a) T = \sum_{t} \chi(at) = \sum_{s} \chi(s) = T
$$
Now since $\chi(a)\neq 1$, $T = 0$.

---
#### Note:
1. The characters on $\mathbb{F}_{p}$ form a group, with group operation defined as pointwise multiplication.
2. And inverses just reciprocals in the normal sense. $\chi^{-1}(a) := \chi(a) ^{-1}$.
3. Identity is $\varepsilon$.

### Proposition 3:
```ad-note
title:
The group of characters is of order $p-1$. If $a \in \mathbb{F}_{p}^{*}$ and $a \neq 1$, then there is a character such that $\chi(a) \neq 1$.
```
###### Proof:
Since $\mathbb{F}_{p}^{*}$ is cyclic, it has a generator say $g$. Then any character is determined by its value at $g$.
Since $\chi(g)$ is a $(p-1)$th root of unity, there are exactly $p-1$ values of $\chi(g)$ and so the group of characters has order at most $p-1$.

Define $\lambda(g ^{k}) = e ^{2\pi ik/(p-1)}$, note that this is a character.
Now we show that $\varepsilon, \lambda, \lambda^{2}, \dots \lambda^{p-2}$ are all distinct.
Let $\lambda^n =\varepsilon$, then $\lambda(g)^n = 1 = e ^{2\pi in /(p-1)} \implies p-1 | n$.
Hence, $p-1$ is the smallest integer $n$ such that $\lambda^n = \varepsilon$.
$\lambda$ has order $p-1$ and so the group of characters is cyclic of order $p-1$.

If $a \in \mathbb{F}_{p}^{*}$, then $a = g ^{l}$ for some $p-1 \nmid l$. Then $\lambda(g^l) = e ^{2\pi il/(p-1)} \neq 1$.

### Corollary
```ad-note
title:
If $a \in \mathbb{F}_{p}^{*}$ and $a \neq 1$, then $\sum_{\chi} \chi(a) = 0$ where the sum is over all characters.
```
###### Proof:
Let the sum be $T$. Since $a\neq 1$, there is a character $\rho$ such that $\rho(a) \neq 1$, then $$\rho(a) T = \sum_{\chi}\rho \chi(a) = \sum_{\chi}\chi(a) = T$$
Since $\rho(a)\neq 1$, $T = 0$.

---
#### Note: Characters are useful to study equations.
Consider $x ^{n} = a$ for $a \in \mathbb{F}_{p}^{*}$. By [[nth Power Residues]] we know that this has a solution iff $a^{(p-1/d)} = 1$. where $d = (n,p-1)$ is the the gcd of $n,p-1$, and that if a solution exists then $d$ solutions exist.

### Proposition 4:
```ad-note
title:
If $a \in \mathbb{F}_p^*$, $n | p-1$ and $x^n=a$ is not solvable then there exists a character such that 
1. $\chi(a) \neq 1$
2. $\chi^n = \varepsilon$
```
###### Proof:
Take $\chi = \lambda^{(p-1)/n}$, then it has order $n$. We know that $a = g^k$ such that $n \nmid k$, since $x^n =a$ is not solvable.
Now $\chi(a) = \lambda(a) ^{p-1/n} = \lambda(g)^{k(p-1)/n} = e ^{2\pi ik/n} \neq 1$.

### Proposition 5:
```ad-note
title:
Let $N(x ^{n} = a)$ denote the number of solutions of $x ^{n} = a$, then $$
N(x ^{n} = a) = \sum_{\chi^{n} = \varepsilon} \chi(a)$$
where the sum is over all characters of order dividing $n$ (they form a group).
```
###### Proof:
If $x ^{n} = a$ is not solvable, then there is a $\rho$ such that $\rho(a) \neq 1$ and $\rho^{n} = \varepsilon$. 
Now $$
\rho(a) N(x ^{n} = a) = \sum_{\chi^{n} = \varepsilon} \rho \chi(a) = \sum_{\chi^{n} = \varepsilon}\chi(a) = N(x ^{n} = a)
$$
Giving $N(x ^{n} = a)=0$ as required.

If $x ^{n} = a$ is solvable, then we need to show that the sum is equal to $(n,p-1) = n$. 
First we show that there are exactly $n$ characters of order dividing $n$.
Let $\chi$ be such a character then $\chi(g)$ is an n-th root of unity, and since there are at most $n$ such roots, there are at most $n$ such characters.
Let $\chi(g) = e ^{2\pi i/n}$, then $\varepsilon,\chi,\chi^{2},\dots,\chi^{n-1}$ are all distinct characters of order dividing $n$, hence proof.

Now there is a $\beta \in \mathbb{F}_{p} ^{*}$ such that $\beta^{n} = a$, and so, $$
\sum_{\chi^{n} = \varepsilon} \chi(a) = \sum_{\chi^{n} = \varepsilon} \chi(\beta^{n}) = \sum_{\chi^{n} = \varepsilon} \chi^{n}(\beta) = \sum_{\chi^{n} = \varepsilon} \varepsilon(\beta) = n
$$.


---
# References
[[Groups]]
[[Finite Fields]]
[[nth Power Residues]]
