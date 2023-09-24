202305261605

Type : #Note
Tags : [[Number Theory]]

---
# Gauss sums
```ad-note
title:
Let $\chi$ be a character on $\mathbb{F}_{p}$ and $a \in \mathbb{F}_{p}$. Set $g_{a}(\chi) = \sum_{t} \chi(t) \zeta^{at}$, where the sum is over all $t \in \mathbb{F}_{p}$. and $\zeta = e ^{2\pi i /p}$. 
$g_{a}(\chi)$ is called a **Gauss sum** on $\mathbb{F}_{p}$ belonging to the character $\chi$.
```

### Proposition 1:
```ad-note
title:
If $a\neq 0$ and $\chi \neq \varepsilon$, then $g_{a}(\chi) = \chi(a ^{-1})g_{1}(\chi)$.

If $a\neq 0$ and $\chi = \varepsilon$, then $g_{a}(\chi) = 0$.

If $a = 0$ and $\chi \neq \varepsilon$, then $g_{0}(\chi) = 0$.

If $a = 0$ and $\chi = \varepsilon$, then $g_{0}(\varepsilon) = p$.
```

##### From now on we denote $g_1(\chi) = g(\chi)$.

### Proposition 2:
```ad-note
title:
If $\chi \neq \varepsilon$, then $|g(\chi)| = \sqrt[]{ p }$.
```
###### Proof:
Idea is to evaluate $\sum_{a}g_a(\chi)\overline{g_{a}(\chi)}$ in two ways.
First, we know $g_{a}(\chi) = \chi(a ^{-1})g(\chi)$. 
This means $$
\sum_{a} g_{a}(\chi)\overline{g_{a}(\chi)} = \sum_{a}\chi(a ^{-1})\overline{\chi(a ^{-1})} g(\chi)\overline{g(\chi)} = \sum_{a\neq 0} g(\chi)\overline{g(\chi)} = (p-1)|g(\chi)|^{2}
$$
Also, 
$$
\begin{align*}
\sum_{a}g_{a}(\chi)\overline{g_{a}(\chi)} &= \sum_{a}\left( \sum_{t}\chi(t) \zeta^{at} \right) \left( \sum_{s} \chi(s) ^{-1}\zeta^{-as} \right) \\ 
&= \sum_{a} \sum_{t,s} \chi(t)\chi(s) ^{-1} \zeta^{a(t-s)}\\ 
&= \sum_{t,s}\chi(ts ^{-1})p \cdot \delta(t,s) \\ 
&= p(p-1)
\end{align*}
$$
Here $\delta(t,s) = 1$ if $t=s$ and 0 otherwise.
Implying $|g(\chi)|^{2} = p$ as desired.

### Lemma:
```ad-note
title:
1. $\overline{g(\chi)}= \chi(-1)g(\overline\chi)$
2. $\chi(-1)p = g(\chi)g(\overline{\chi})$
```
###### Proof:
1. 
$$
\begin{align*}
\overline{g(\chi)} &= \sum_{t} \overline{\chi(t)}\zeta^{-t} \\ 
&= \sum_{t}\overline{\chi(-1)}\overline{\chi(-t)} \zeta^{-t} \\
&= \chi(-1) \sum_{t}\overline{\chi(t)}\zeta^{-t}\\
&= \chi(-1)g(\overline{\chi})
\end{align*}
$$
2. We know from proposition 2, $p = |g(\chi)|^{2} = g(\chi)\overline{g(\chi)} = g(\chi)g(\overline{\chi})\chi(-1)$.

### Theorem 1:
```ad-note
title:
For a quadratic gauss sum (a gauss sum over the quadratic character $\chi$) $g(\chi)$, 
$$
g(\chi) = \begin{cases}
\sqrt{p} & \text{if } p \equiv 1\ (\mathrm{mod} \ 4) \\ 
i\sqrt{p} & \text{if } p \equiv 3\ (\mathrm{mod} \ 4)
\end{cases}
$$
```
###### Proof:
We know $|g(\chi)|^{2} = p$ and $\overline{g(\chi)} = g(\chi)\chi(-1) = g(\chi)\left(\frac{-1}{p} \right)$. This gives $$
g(\chi)^{2}\left( \frac{-1}{p} \right) = p
$$
Hence the result.

---
# References
[[Multiplicative Characters ]]

