202305261905

Type : #Note
Tags : [[Number Theory]]

---
# Jacobi Sums
```ad-info
title: Idea
Consider the equation $x^{2}+y^{2} = 1$ in the field $\mathbb{F}_{p}$. Since $\mathbb{F}_{p}$ is finite, the equation only has finitely many solutions.
Let $N(x^{2}+y^{2} = 1)$ be the number of solutions.
Then,
$$
\begin{align}
N(x^{2}+y^{2} = 1) = \sum_{a+b=1}N(x^{2} =a)N(y^{2}=b)
\end{align}
$$
where $a,b \in \mathbb{F}_{p}$.
Since $N(x^{2} = a) = 1 + \left( \frac{a}{p} \right)$ (refer to [[Multiplicative Characters]]), substituting we get:
$$
\begin{align}
N(x^{2}+y^{2}=1) &= \sum_{a+b=1}1 + \left( \frac{a}{p} \right) +\left( \frac{b}{p} \right) +\left( \frac{ab}{p} \right) \\
&= p + \sum_{a}\left( \frac{a}{p} \right) +\sum_{b}\left( \frac{b}{p} \right) +\sum_{a+b=1}\left( \frac{ab}{p} \right)  \\
&= p + \sum_{a+b=1}\left( \frac{a}{p} \right) \left( \frac{b}{p} \right) 
\end{align}
$$

Another example,
$$
\begin{align}
N(x^{3}+y^{3}=1) &= \sum_{a+b=1}N(x^{3}=a)N(y^{3}=b)  \\
&= \sum_{a+b=1}\left(\sum_{i=0}^{2}\chi^{i}(a)\right)\left( \sum_{j=0}^{2} \chi^{j}(b) \right) \\
&= \sum_{a+b=1}\left( \sum_{i,j} \chi^{i}(a)\chi^{j}(b) \right)  \\
&= \sum_{i,j}\left( \sum_{a+b=1}\chi^{i}(a)\chi^{j}(b) \right)   
\end{align}
$$
where $\chi$ is a character of order 3. 

This means that understanding sums of the form $\sum_{a+b=1}\chi(a)\lambda(b)$ where $\chi$ and $\lambda$ are characters, will help us understand the number of solutions of equations in $\mathbb{F}_{p}$.
```

```ad-note
title:
Let $\chi$ and $\lambda$ be characters on $\mathbb{F}_{p}$ and set $J(\chi,\gamma) = \sum_{a+b=1}\chi(a)\lambda(b)$. 

$J(\chi,\lambda)$ is called a **Jacobi sum**.
```

### Theorem 1:
```ad-note
title:
Let $\chi$ and $\lambda$ be non trivial characters. Then
1. $J(\varepsilon,\varepsilon) = p$
2. $J(\chi,\varepsilon) = 0$
3. $J(\chi,\chi^{-1}) = -\chi(-1)$
4. If $\chi\lambda \neq \varepsilon$, then $$
J(\chi,\lambda) = \frac{g(\chi)g(\lambda)}{g(\chi\lambda)}
$$
```
###### Proof:
3. $$
\begin{align}
J(\chi,\chi^{-1}) &= \sum_{a+b=1}\chi(a)\chi^{-1}(b) \\
&= \sum_{a+b=1} \chi\left( \frac{a}{b} \right) \\
&= \sum_{a\neq 1} \chi \left( \frac{a}{1-a} \right) \\
&= \sum_{c \neq -1} \chi(c) \\
&= 0-\chi(-1)
\end{align}
$$
We have used the fact that the function $\phi : \mathbb{F}_{p} \setminus \{ 1 \} \to \mathbb{F}_{p} \setminus \{ -1 \}$ taking $a$ to $\frac{a}{1-a}$ is bijective.
4. $$
\begin{align}
g(\chi)g(\lambda) &= \left( \sum_{t} \chi(t)\zeta^{t} \right) \left( \sum_{s}\lambda(s)\zeta^{s} \right) \\
&= \sum_{t,s}\chi(t)\lambda(s)\zeta^{s+t} \\
&= \sum_{t+s=0}\chi(t)\lambda(s)+\sum_{a\neq 0}\sum_{t+s=a}\chi(t)\lambda(s)\zeta^{a} \\
&=\sum_{t}\chi(t)\lambda(-t) + \sum_{a \neq 0} \zeta^{a} \left( \sum_{t'+s' = 1} \chi(at')\lambda(as') \right) \\
&= \lambda(-1)\sum_{t}\chi\lambda(t) + \sum_{a \neq 0} \zeta^{a} \chi\lambda(a) \left( \sum_{t'+s'=1}\chi(t')\lambda(s') \right)  \\
&= 0 + J(\chi,\lambda)g(\chi\lambda)
\end{align}
$$
In the last equality we use the fact that $\chi \lambda$ is non trivial.

### Corollary:
```ad-note
title:
If $\chi,\lambda,\chi\lambda \neq \varepsilon$ then $|J(\chi,\lambda)| = \sqrt[]{ p }$
```

#### NOTE:
- Observe that $\sum_{a+b=1}\left( \frac{a}{p} \right)\left( \frac{b}{p} \right) = J(\chi,\chi^{-1})$ where $\chi$ is the Legendre symbol (character of order 2). And so the value of the sum is $-\chi(-1) = -(-1)^{(p-1)/2}$. This gives a precise value of the number of solutions of the concerned equation.
- Similarly, $$N(x^{3}+y^{3} = 1) = \sum_{i,j}\left( \sum_{a+b=1}\chi^{i}(a)\chi^{j}(b) \right) =p + J(\chi,\chi) + 2J(\chi,\chi^{2}) + J(\chi^{2},\chi^{2}) = p - 2\chi(-1) + J(\chi,\chi) + J(\chi^{2},\chi^{2})$$
Since $\chi(-1) = \chi((-1)^{3}) = \chi(-1)^{3} = \varepsilon(-1) = 1$, we get $$
N(x^{3}+y^{3}=1) = p-2 + 2 \mathrm{Re}(J(\chi,\chi))
$$
Giving us $|N(x^{3}+y^{3}=1) - p+ 2| \le 2 \sqrt[]{ p }$
Which gives us asymptotic information about the number of solutions.

### Proposition 1:
```ad-note
title:
If $p \equiv 1 (\mathrm{mod} \ 4)$ then there exists integers $a,b$ such that $p = a^{2}+b^{2}$.
If $p \equiv 1(\mathrm{mod} \ 3)$ then there exists integers $a,b$ such that $p = a^{2}+b^{2}-ab$.
```
###### Proof:
If $p\equiv 1(\mathrm{mo d} \ 4)$, there is a character $\chi$ of order $4$ on $\mathbb{F}_{p}$, since the order of the group of characters is $p-1$. 
The values this character takes belongs to $\{ \pm {1},\pm i \}$. Hence, $J(\chi,\chi) = \sum_{a+b=1}\chi(a)\chi(b) \in \mathbb{Z}[i]$. 
Noting that $|J(\chi,\chi)|^{2} =p$, we get that $p = (x+yi)(x-yi)$ since $J(\chi,\chi) = x+yi; \ x,y \in \mathbb{Z}$.
Thus, $p = x^{2}+y^{2}$.

If $p \equiv 1(\mathrm{mo d} \ 3)$, there is a character $\chi$ of order 3 on $\mathbb{F}_{p}$.
The values this character takes belongs to $\{ {1},\omega,\omega^{2}\}$. Hence, $J(\chi,\chi) = \sum_{a+b=1}\chi(a)\chi(b) \in \mathbb{Z}[\omega]$. 
Noting that $|J(\chi,\chi)|^{2} =p$, we get that $p = (x+y \omega)(x+y \omega^{2})$ since $J(\chi,\chi) = x+y \omega; \ x,y \in \mathbb{Z}$.
Thus, $p = x^{2}+y^{2} -xy$.

#### Note:
1. We can show that $p = a^{2}+b^{2}$ is a unique representation given that $a$ is odd and $b$ is even, and $a,b > 0$. (Just use unique factorisation in $\mathbb{Z}[i]$).
2. The representation $p = a^{2}+b^{2}-ab$ is not unique even if we assume that $a,b > 0$.
   $$
a^{2}+b^{2}-ab = (b-a)^{2}+b^{2}-(b-a)b = (a-b)^{2}+a^{2}-(a-b)a
$$
3. But we can reformulate the result so that it is unique. 
   If $p=a^{2}+b^{2}-ab$ then $4p = (2a-b)^{2}+3b^{2} = (2b-a)^{2}+3a^{2} = (a+b)^{2} + 3(a-b)^{2}$.
   We claim that $3$ divides either $b,a$ or $(a-b)$. Suppose $3 \nmid a,b$ and $a \equiv 1 (\mathrm{mo d}\ 3)$ and $b \equiv 2(\mathrm{mo d}\ 3)$ then 
   $p \equiv 0 (\mathrm{mo d}\ 3)$ that's a contradiction.
   Similarly $a \equiv 2(\mathrm{mo d}\ 3)$ and $b \equiv 1(\mathrm{mo d}\ 3)$ gives the same contradiction.

This gives the following proposition:
### Proposition 2:
```ad-note
title:
If $p \equiv 1(\mathrm{ mo d}\ 3)$ then there are integers $A,B$ such that $4p = A^{2}+27B^{2}$. In this representation of $4p$, $A,B$ are uniquely determined up to sign.
```
###### Proof:
Since $A$ is not divisible by $3$, $A \equiv 1,2(\mathrm{mo d}\ 3)$. But since we can replace $A$ by $-A$, WLOG we can assume that $A \equiv 1 (\mathrm{mo d}\ 3)$.
So we show that under the assumption $A \equiv 1(\mathrm{mo d} \ 3)$, the representation is unique.
$$
\begin{align}
4p = (A + 3 \sqrt[]{ 3 }iB)(A-3 \sqrt[]{ 3 }iB) &= ((A+3B) + 6B \omega)(A-3B - 6B \omega)  \\
\implies p &= \left( \frac{A+3B}{2} + 3B \omega \right) \left( \frac{A-3B}{2}-3B \omega \right)  \\
\implies p &= \pi \overline{\pi} 
\end{align}
$$
where $\pi = \frac{A+3B}{2}+3B \omega$.
$\pi$ is a prime since its norm is a prime in $\mathbb{Z}$.

Now if $4p = C^{2}+27D^{2}$, with $C \equiv 1(\mathrm{mo d}\ 3)$, then $$
p = \left( \frac{A+3B}{2} + 3B \omega \right) \left( \frac{A-3B}{2}-3B \omega \right) = \left( \frac{C+3D}{2}+3D \omega \right) \left( \frac{C-3D}{2}-3D \omega \right)
$$
Since $\mathbb{Z}[\omega]$ is a UFD, $\left( \frac{A+3B}{2} +3B \omega\right)$ and $\left( \frac{C + 3D}{2} + 3D \omega \right)$ are associates WLOG, since we can replace $D$ by $-D$ if necessary.
Therefore one of the following holds:
$$
\begin{align}
\left( \frac{A+3B}{2} +3B \omega\right) &= \pm \left( \frac{C + 3D}{2} + 3D \omega\right)  \\
&= \pm \omega \left( \frac{C + 3D}{2} + 3D \omega\right)  \\
&= \pm \omega^{2} \left( \frac{C + 3D}{2} + 3D \omega\right) 
\end{align}
$$
By exhausting each case, we see that $$
\left( \frac{A+3B}{2}+3B \omega \right)  = \left( \frac{C+3D}{2} + 3D \omega \right)
$$
is the only possibility.
Hence, $A = C$ as desired.

### Proposition 3:
```ad-note
title:
Suppose that $p \equiv 1(\mathrm{mo d}\ n)$ and that the character $\chi$ is of order $n > 2$. Then $$
g(\chi)^{n} = p\chi(-1)J(\chi,\chi)J(\chi,\chi^{2})\dots J(\chi,\chi^{n-2})
$$
```
###### Proof:
We know that $g(\chi)^{2} = g(\chi^{2})J(\chi,\chi)$ (by part (4) of theorem 1).
$g(\chi)^{3} = J(\chi,\chi)g(\chi^{2})g(\chi) = J(\chi,\chi)J(\chi,\chi^{2})g(\chi^{3})$
Proceeding this way,
$g(\chi) ^{n-1} = J(\chi,\chi)\dots J(\chi,\chi^{n-2})g(\chi^{n-1})$
$g(\chi)^{n} = J(\chi,\chi)\dots J(\chi,\chi^{n-2}) g(\chi^{-1})g(\chi)$
But $g(\chi^{-1}) = g(\overline{\chi}) = \overline{g(\chi)}\chi(-1)$.

Hence, $g(\chi)^{n} = J(\chi,\chi)\dots J(\chi,\chi^{n-2})|g(\chi)|^{2}\chi(-1)$
$\implies g(\chi)^{n} = p\chi(-1)J(\chi,\chi)\dots J(\chi,\chi^{p-2})$.

### Corollary:
```ad-note
title:
If $\chi$ is a cubic character, then $$
g(\chi)^{3} = pJ(\chi,\chi)
$$
```

#### Note:
Looking at $N(x^{3}+y^{3}=1)$ again, we have seen that $J(\chi,\chi) = a+b \omega$ where $\chi$ is a character of order 3.

### Proposition 4:
```ad-note
title:
Suppose $p \equiv 1(\mathrm{mo d}\ 3)$ and that $\chi$ is a cubic character. Set $J(\chi,\chi) = a+b \omega$. Then 

a) $b\equiv 0(\mathrm{mo d}\ 3)$

b) $a \equiv 2(\mathrm{mo d}\ 3)$
```
###### Proof:
$$
\begin{align}
g(\chi)^{3} = \left(\sum_{t}\chi(t)\zeta^{t}\right)^{3} &\equiv \sum_{t}\chi(t)^{3}\zeta^{3t} \ (3)  \\
&\equiv  \sum_{t \neq 0}\zeta^{3t} \ (3) \\
&\equiv -1 \ (3)
\end{align}
$$
This gives $pJ(\chi,\chi) \equiv J(\chi,\chi) \equiv 2 \ (3)$. This gives the result.

### Corollary:
```ad-note
title:
Let $A = 2a-b$ and $B = \frac{b}{3}$. Then $A\equiv 1 \ (3)$ and $4p =A^{2}+27B^{2}$.
```
###### Proof:
Since $J(\chi,\chi) = a+b \omega$ and $|J(\chi,\chi)|^{2} = p$, we have $p = a^{2}+b^{2}-ab$.
Thus $4p = (2a-b)^{2}+3b^{2}$ and $4p = A^{2}+27B^{2}$.

By the previous proposition, $3 \mid b$ and $a \equiv 2 \ (3)$, hence $A \equiv 1 \ (3)$.

### Theorem 2:
```ad-note
title:
Suppose that $p \equiv 1 \ (3)$. Then there are integers $A,B$ such that $4p = A^{2}+27B^{2}$. If we require that $A \equiv 1 \ (3)$ then $A$ is uniquely determined and $$
N(x^{3}+y^{3}=1) = p-2 + A
$$
```
###### Proof:
We have shown that $N(x^{3}+y^{3}=1) = p-2 + 2 \mathrm{Re}(J(\chi,\chi))$. Since $J(\chi,\chi) = a+b \omega$, $\mathrm{Re}(J(\chi,\chi)) = \mathrm{Re}\left( a + b\left( \frac{-1 + \sqrt[]{ 3 }}{2}\right) \right) = \frac{2a-b}{2}$.
This gives the required formula since $A = 2a-b$. We have also shown uniqueness before.

---
# Generalised Jacobi Sums

### Definition:
```ad-note
title:
Let $\chi_{1},\chi_{2},\dots \chi_{l}$ be characters on $\mathbb{F}_{p}$. A Jacobi sum is defined by $$
J(\chi_{1},\chi_{2},\dots \chi_{l}) = \sum_{t_{1}+\dots+t_{l} = 1}\chi_{1}(t_{1})\chi_{2}(t_{2})\dots \chi_{l}(t_{l})
$$
```

### Definition:
```ad-note
title:
$J_{0}(\chi_{1},\dots \chi_{l}) = \sum_{t_{1}+\dots+t_{l}=0}\chi_{1}(t_{1})\dots \chi_{l}(t_{l})$.
```

### Proposition 5:
```ad-note
title:
1. $J_{0}(\varepsilon,\varepsilon,\dots,\varepsilon) = J(\varepsilon,\varepsilon, \dots,\varepsilon) = p ^{l-1}$
2. If some but not all of the $\chi_{i}'s$ are trivial, then $J_{0} = J = 0$.
3. Assume that $\chi_{l} \neq \varepsilon$. Then $$
J_{0}(\chi_{1},\dots \chi_{l}) = \begin{cases}
0, \ \ &\text{if } \chi_{1}\chi_{2}\dots \chi_{l} \neq \varepsilon  \\
\chi_{l}(-1)(p-1)J(\chi_{1},\dots \chi_{l-1}), \ &\text{otherwise}
\end{cases}
$$
```
###### Proof:
1. $$
\begin{align}
J_{0}(\varepsilon,\varepsilon, \dots \varepsilon) = \sum_{t_{1}+t_{2}+\dots+t_{l}  = 0} 1 = p ^{l-1} = J(\varepsilon, \varepsilon \dots \varepsilon)
\end{align}
$$
2. $$
\begin{align}
J_{0}(\chi_{1},\dots,\chi_{l-1},\varepsilon) &= \sum_{t_{1}+\dots+t_{l-1}+ t_{l} = 0} \chi_{1}(t_{1})\dots \chi_{l-1}(t_{l-1}) \\
&= \sum_{t_{1},t_{2},\dots t_{l-1}} \chi_{1}(t_{1})\chi_{2}(t_{2})\dots \chi_{l-1}(t_{l-1}) \\
&= \prod\left( \sum_{t_{i}}\chi_{i}(t_{i}) \right) = 0
\end{align}
$$
Since at least one of the terms in the product is 0.

3. $$
\begin{align}
J_{0}(\chi_{1},\chi_{2},\dots \chi_{l}) &= \sum_{t_{1}+t_{2}+\dots+t_{l}=0} \chi_{1}(t_{1})\chi_{2}(t_{2})\dots \chi_{l}(t_{l}) \\
&= \sum_{t_{l}\neq 0}\sum_{t_{1}+t_{2}+\dots+t_{l-1} = -t_{l}} \chi_{1}(t_{1})\dots \chi_{l-1}(t_{l-1})\chi_{l}(t_{l})  \\
&= \sum_{t_{l}\neq 0} \sum_{t_{1}'+\dots+t_{l-1}' = 1} \chi_{1}(-t_{l}t_{1}')\dots \chi_{l-1}(-t_{l}t_{l-1}')\chi_{l}(t_{l})  \\
&= \sum_{t_{l}\neq 0}(\chi_{1}\chi_{2}\dots \chi_{l})(-t_{l})\chi_{l}(-1) J(\chi_{1},\chi_{2},\dots \chi_{l}) \\
&= \chi_{l}(-1)J(\chi_{1},\chi_{2},\dots \chi_{l-1}) (g(\chi_{1}\chi_{2}\dots \chi_{l}) - \chi_{1}\chi_{2}\dots \chi_{l}(0))
\end{align}
$$
This gives the desired result.

### Theorem 3:
```ad-note
title:
```
```ad-note
title:
Assume that $\chi_{1},\chi_{2},\dots \chi_{l}$ are non trivial and their product is also non trivial.
Then $$
g(\chi_{1})g(\chi_{2})\dots g(\chi_{l}) = J(\chi_{1},\chi_{2},\dots \chi_{l})g(\chi_{1}\chi_{2}\dots \chi_{l})
$$
```
###### Proof:
$$
\begin{align}
g(\chi_{1})\dots g(\chi_{l}) &= \prod_{i=1}^{l}\sum_{t}\chi_{i}(t)\zeta^{t}  \\
&= \sum_{s=0}^{p-1}\sum_{t_{1}+t_{2}+\dots t_{l} = s} \chi_{1}(t_{1})\dots \chi_{l}(t_{l})\zeta^{s}  \\
&= J_{0}(\chi_{1},\chi_{2},\dots \chi_{l}) + \sum_{s=1}^{p-1}\zeta^{s}\left( \sum_{t_{1}'+t_{2}'\dots+t_{l}' = 1}\chi_{1}\chi_{2}\dots \chi_{l}(s) \chi_{1}(t_{1})\chi_{2}(t_{2})\dots \chi_{l}(t_{l}) \right) \\
&= J_{0}(\chi_{1},\chi_{2},\dots \chi_{l}) + \sum_{s = 1}^{p-1}\zeta^{s}\chi_{1}\chi_{2}\dots \chi_{l}(s)J(\chi_{1},\dots \chi_{l}) \\
&=  0 + J(\chi_{1},\chi_{2},\dots \chi_{l})g(\chi_{1}\dots \chi_{l})
\end{align}
$$

### Corollary 1:
```ad-note
title:
Suppose that $\chi_{1},\chi_{2},\dots \chi_{l}$ were non trivial but their product is trivial.
Then $$
g(\chi_{1})\dots g(\chi_{l})= \chi_{l}(-1)p J(\chi_{1},\dots \chi_{l-1})
$$ 
```
###### Proof:
We know $$
\begin{align}
g(\chi_{1})\dots g(\chi_{l-1}) &= g(\chi_{1}\dots \chi_{l-1})J(\chi_{1},\dots \chi_{l-1})  \\
\implies g(\chi_{1})\dots g(\chi_{l}) &= g(\chi_{1}\dots \chi_{l-1})g(\chi_{l})L(\chi_{1},\chi_{2},\dots \chi_{l-1}) \\
&= g(\overline{\chi_{l}})g(\chi_{l})J(\chi_{1},\dots \chi_{l-1}) \\
&= p\chi_{l}(-1)J(\chi_{1},\dots \chi_{l-1})
\end{align}
$$
### Corollary 2:
```ad-note
title:
Let the hypotheses as in corollary 1, then $$
J(\chi_{1},\dots \chi_{l}) = - \chi_{l}(-1)J(\chi_{1},\dots \chi_{l-1})
$$
```
###### Proof:
We know $(\sum_{s=1}^{p-1}\zeta^{s} )J(\chi_{1},\dots ,\chi_{l}) + J_{0}(\chi_{1},\dots \chi_{l}) = g(\chi_{1})g(\chi_{2})\dots g(\chi_{l})$, from the proof of theorem 3.
This means $$
\begin{align}
J(\chi_{1},\dots \chi_{l}) &= -g(\chi_{1})g(\chi_{2})\dots g(\chi_{l}) + J_{0}(\chi_{1},\dots \chi_{l}) \\
&= \chi_{l}(-1)(p-1)J(\chi_{1},\dots \chi_{l-1}) - \chi_{l}(-1)pJ(\chi_{1},\dots \chi_{l}) \\
&= -\chi_{l}(-1)J(\chi_{1},\dots \chi_{l-1})
\end{align}
$$

### Theorem 4:
Assume that $\chi_{1},\dots \chi_{r}$ are non trivial.
1. If $\chi_{1}\dots \chi_{r}\neq\varepsilon$, then $$
|J(\chi_{1},\chi_{2},\dots \chi_{r})| = p ^{(r-1)/2}
$$
2. If $\chi_{1}\dots \chi_{r}= \varepsilon$, then $$
|J_{0}(\chi_{1},\dots,\chi_{r})| = (p-1)p ^{r/2-1}
$$
and $$
|J(\chi_{1},\dots \chi_{r})| = p ^{r/2-1}
$$


---
# References
[[Gauss sums]]
[[Multiplicative Characters]]
