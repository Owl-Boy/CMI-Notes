---
tags:
  - Note
  - Incomplete
---
202401091401

Tags : [[Expander Graphs and Applications]]
# Expander Mixing Lemma
---

> [!idea] In words:
> The expander mixing lemma states that the edges of $d-$regular expander graphs are evenly distributed throughout the graph. In particular the number of edges between two vertex subsets $S$ and $T$ is always close to the expected number of edges between them in a random $d-$regular graph, which is $\frac{d}{n}|S||T|.$

**Lemma:** Let $G$ be a $(n,d,\lambda)$ graph. Let $S,T\subseteq V$, then
$$
\left||e(S,T)|- \frac{d|S||T|}{n}\right|\leq\lambda d\sqrt{ |S||T| }.
$$
*Proof:*
Let $u=\left( \frac{1}{\sqrt{ n }}, \frac{1}{\sqrt{ n }},\dots, \frac{1}{\sqrt{ n }} \right)^{T}$, (the normalised uniform vector), $\|u\|_{2}=1$.

> [!info] *Fact:* Any vector $v\perp u$, $\|Av\|_{2}\leq\lambda\|v\|_{2}$.
 $v=\sum\limits_{i=2}^{n}\beta_{i}v_{i}$, where $\{ u,v_{2},\dots,v_{n} \}$ spans $\mathbb{R}^{n}$. $Av=\sum\limits_{i=2}^{n}\beta_{i}Av_{i}=\sum\limits_{i=2}^{n}\beta_{i}\lambda_{i}v_{i}$.
 Assuming $|\lambda_{2}|\geq|\lambda_{3}|\geq\dots\geq|\lambda_{n}|$, $\| Av \|_{2}\leq |\lambda_{2}|.\| \sum\limits_{i=2}^{n}\beta_{i}v_{i} \|_{2}=|\lambda_{2}|.\| v \|_{2}$
 In fact, $\lambda_{2}=\max\limits_{v\perp u} \frac{\| Av \|_{2}}{\| v \|_{2}}$. (Take $v=v_{2}$.)

Let $\chi_{S},\chi_{T}$ be the characteristic vectors for $S,T$.
$$
\chi_{S}(i)=\left\{
\begin{align*}
1 && \text{iff } i \in S,\\
0 && \text{otherwise.}
\end{align*}
\right.
$$
> [!seealso] Remember Cauchy-Schwarz:
 $|\langle x,y \rangle|\leq \|x\|_{2}\|y\|_{2}$.

$e(S,T)=d\chi_{S}^{T}A\chi_{T}$.

Break $\chi_{S}$ and $\chi_{T}$ into components along $u$ and perpendicular to $u$, to get $\chi_{S}=\alpha u+\chi_{S}^{\perp_{u}}$, and $\chi_{T}=\beta u+\chi_{T}^{\perp_{u}}$.
Here $\alpha= \langle \chi_{S},u \rangle= \frac{|S|}{\sqrt{ n }}$, and $\beta=\langle \chi_{T},u \rangle= \frac{|T|}{\sqrt{ n }}$.

So,
$$
\begin{align}
e(S,T)&=d.(\alpha u^{T}+(\chi_{S}^{\perp_{u}})^{T}).A.(\beta u+\chi_{T}^{\perp_{u}}) \\
&=d.(\alpha\beta (u^{T}Au)+0+0+((\chi_{S}^{\perp_{u}})^{T}A\chi_{T}^{\perp_{u}})) \\
&=\frac{d|S||T|}{n}+d.((\chi_{S}^{\perp_{u}})^{T}A\chi_{T}^{\perp_{u}}) \\
\left|e(S,T)-\frac{d|S||T|}{n}\right|&=d.\left|(\chi_{S}^{\perp_{u}})^{T}A\chi_{T}^{\perp_{u}}\right|
\end{align}
$$

Using Cauchy-Schwarz, we get
$$
\begin{align}
\left|(\chi_{S}^{\perp_{u}})^{T}A\chi_{T}^{\perp_{u}}\right|&\leq \| \chi_{S}^{\perp_{u}} \|\| A\chi_{T}^{\perp_{u}} \|  \\
&\leq\lambda \| \chi_{S}^{\perp_{u}} \| \| \chi_{T}^{\perp_{u}} \|  \\
&\leq\lambda \| \chi_{S} \| \| \chi_{T} \|  \\
&=\lambda \sqrt{ |S||T| }.
\end{align}
$$
---

# References
