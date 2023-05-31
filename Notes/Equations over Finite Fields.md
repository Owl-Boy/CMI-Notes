202305271605

Type : #Note
Tags : [[Number Theory]] [[Algebra]]

---
# Equation $x ^{n}+y ^{n} = 1$ in the field $\mathbb{F}_{p}$.
Assume $p \equiv 1\ (n)$ and consider the equation $x ^{n}+y ^{n} = 1$ in the field $\mathbb{F}_{p}$.

We have $N(x ^{n}+ y ^{n} = 1) = \sum_{a+b=1}N(x ^{n}= a)N(y ^{n} = a)$.
Let $\chi$ be a character of order $n$.
Then $$
\begin{align}
N(x ^{n}+y ^{n} = 1) &= \sum_{a+b=1} \left( \sum_{i=0}^{n-1}\chi^{i}(a) \right)\left( \sum_{j=0}^{n-1}\chi^{j}(b) \right)   \\
&= \sum_{i,j} J(\chi^{i},\chi^{j})
\end{align}
$$
When $i = j = 0$, $J(\varepsilon,\varepsilon) = p$.
When $i + j =n$, $J(\chi^{i},\chi^{j}) = -\chi^{i}(-1)$. The sum of these terms is $-\sum_{i=1}^{n-1}\chi^{i}(-1) = 1 - \delta_{n}(-1)$ where $\delta_{n}(-1) = 1$ if $-1$ is an nth power and 0 otherwise.
When $i = 0, j\neq 0$ and $j = 0, i\neq 0$ then $J(\chi^{i},\chi^{j}) = 0$

Hence $$
N(x ^{n} + y ^{n} = 1) = p + (1- \delta_{n}(-1)) + \sum_{1 \le i, j \le n-1\ ; \  i+j \neq n} J(\chi^{i},\chi^{j})
$$
This gives $$
|N(x ^{n} + y ^{n} = 1) - p -(1-\delta_{n}(-1))| \le (n-1)(n-2)\sqrt[]{ p }
$$
----
# The equation $x_{1}^{2}+x_{2}^{2}+\dots x_{r}^{2} =  1$ over $\mathbb{F}_{p}$.
Let $\chi$ be a character of order $2$ ($\chi(a) = \left( \frac{a}{p} \right)$).
Then $$
\begin{align}
N(x_{1}^{2} + \dots x_{r}^{2} = 1) &= \sum_{t_{1}+t_{2}+\dots t_{r} = 1}N(x_{1}^{2}=t_{1})\dots N(x_{r}^{2} = 1)  \\
&= J(\varepsilon,\varepsilon,\dots,\varepsilon) + J(\chi,\chi, \dots,\chi) \\
&= p ^{r-1} + J(\chi,\chi, \dots,\chi)
\end{align}
$$
If $r$ is odd, then $g(\chi)^{r} = g(\chi)J(\chi, \dots ,\chi) \implies J(\chi, \dots ,\chi) = g ^{r-1}(\chi)$.
Since $g ^{2}(\chi) = g(\chi)g(\overline{\chi}) = g(\chi)\overline{g(\chi)}\chi(-1) = p\chi(-1) = p(-1)^{(p-1)/2}$ 
Therefore, $g ^{r-1}(\chi) = p ^{(r-1)/2}(-1)^{(p-1)(r-1)/4}$.

If $r$ is even, then $J(\chi,\chi\dots,\chi) = -\chi(-1)J(\chi, \dots ,\chi)$ where the term on the right has $r-1$ $\chi's$.
This equals $-\chi(-1)p ^{(r-2)/2}\chi(-1)^{(r-2)/2} = -\chi(-1)^{r/2}p ^{r/2-1}$

### Proposition:
```ad-note
title:
If $r$ is odd, then 
$$
N(x_{1}^{2}+x_{2}^{2}+\dots+x_{r}^{2} = 1) = p ^{r-1} + p ^{(r-1)/2}(-1)^{((r-1)/2)((p-1)/2)}
$$
If $r$ is even, then $$
N(x_{1}^{2}+x_{2}^{2}+\dots+x_{r}^{2} = 1) = p ^{r-1} - p ^{r/2-1}(-1)^{(r/2)((p-1)/2)}
$$
```

---
# $a_{1}x_{1}^{l_{1}} + \dots + a_{r}x_{r}^{l_{r}} = b$ over $\mathbb{F}_{p}$
Here $a_1,a_{2},\dots a_{r} \in \mathbb{F}_{p}^{*}$ and $b \in \mathbb{F}_{p}$.
Let $N$ be the number of solutions. Then $$
N = \sum_{a_{1}t_{1}+ \dots a_{r}t_{r} = b} N(x_{1}^{l_{1}} = t_{1})\dots N(x_{r}^{l_{r}}=t_r)
$$
Note that $N(x ^{m} = a) = N(x ^{d} = a)$ where $d = (m,p-1)$.
Indeed, $$N(x ^{m} = a) = \begin{cases}
d &  \text{if } a ^{(p-1)/d} = 1\\
0 & \text{otherwise}
\end{cases}$$
And so, $N(x ^{m} = a) = \sum_{\chi}\chi(a)$ where the sum is over characters $\chi$ such that $\chi^{d} = \varepsilon$ (similar to proposition 5 in [[Multiplicative Characters]]).
We can show that if $x ^{m} = a$ is unsolvable, then the character $\chi = \lambda^{(p-1)/d}$ is such that $\chi^{d} = \varepsilon$, and $\chi(a) \neq 1$ (this helps us prove the above expression for $N(x ^{m} = a)$).

So we can replace the $l_{i}'s$ by $gcd(l_{i},p-1)$ and hence assume $l_{i} | p-1$.
Now let $\chi_{i}$ vary over the characters with order dividing $l_{i}$.

$$
\begin{align}
	N(x ^{m} = a) &= \sum_{\chi_{1},\dots \chi_{r}}\sum_{a_{1}t_{1} + \dots +a_{r}t_{r} = b} \chi_{1}(t_{1})\dots \chi_{r}(t_{r})
\end{align}
$$
If $b = 0$, let $u_{i} = a_{i}t_{i}$. Then the inner sum becomes $$
\sum_{u_{1}+\dots+u_{r} = 0}\chi_{1}\left( \frac{u_{1}}{a_{1}} \right)\dots \chi_{r}\left( \frac{u_{r}}{a_{r}} \right) = \chi_{1} ^{-1}(a_{1})\dots \chi_{r}^{-1}(a_{r})J_{0}(\chi_{1},\chi_{2},\dots, \chi_{r})
$$
If $b\neq 0$, let $u_{i} = b ^{-1} a_{i}t_{i}$ and the inner sum becomes $$
\sum_{u_{1}+\dots+u_{r}=  1} \prod\chi_{i}(ba_{i}^{-1}u_{i}) = \chi_{1}\chi_{2}\dots \chi_{r}(b)\chi_{1}^{-1}(a_{1})\dots \chi_{r}^{-1}(a_{r})J(\chi_{1},\dots,\chi_{r})
$$
In both cases, if $\chi_{1} = \dots =\chi_{r} = \varepsilon$, the value becomes $p ^{r-1}$.
If some but not all $\chi_{i}$'s are trivial, the value becomes 0.
In the first case, the value is zero unless $\chi_{1}\dots \chi_{r} = \varepsilon$.

### Proposition:
```ad-note
title:
If $b=0$ then $$N = p ^{r-1} + \sum \chi_{1}(a_{1}^{-1})\dots \chi_{r}(a_{r}^{-1})J_{0}(\chi_{1},\dots \chi_{r})$$

here the sum is over all r-tuples of characters such that $\chi_{i}^{l_{i}}=\varepsilon$, $\chi_{i} \neq \varepsilon$ for $i = 1,2,\dots r$ and $\chi_{1}\dots \chi _r=\varepsilon$.


If $b \neq 0$, then $$N = p ^{r-1} + \sum\chi_{1}\chi_{2}\dots \chi_{r}(b)\chi_{1}^{-1}(a_{1})\dots \chi_{r}^{-1}(a_{r})J(\chi_{1},\dots,\chi_{r})$$

here the sum is over all r-tuples of characters such that $\chi_{i}^{l_{i}}=\varepsilon$, $\chi_{i} \neq \varepsilon$ for $i = 1,2,\dots r$.
If $M_{0}$ is the number of such $r$-tuples with $\chi_{1}\dots \chi_{r} = \varepsilon$, and $M_{1}$ the number of tuples with $\chi_{1}\dots \chi_{r}\neq\varepsilon$, then 
$$|N-p ^{r-1} | \le M_{0}p ^{(r/2)-1} + M_{1}p ^{(r-1)/2}$$
```

---
# References
[[Finite Fields]]
[[Jacobi Sums]]
[[Multiplicative Characters]]