---
tags:
  - Note
  - Incomplete
---
202402202302

Tags : [[Expander Graphs and Applications]]
# Expander Graphs
---
$G=(V,E)$. $G$ is $d-$regular. By default, graphs are undirected. Now something should expand. A natural way is the neighbouring set of a set being bigger in size.

**Neighbourhood set:** $\forall S\subseteq V$, $N(S):=\{ v\in V\setminus S \mid \exists u\in S, (u,v)\in E \}$.

## Vertex Expansion
---
**Definition:** If we take any subset $S$ of vertices of size at most some $\alpha n$, then the neighbourhood set has size at least $\gamma |S|$, $|N(S)|\geq\gamma |S|$. The graph then is known as a $\gamma-$vertex expander.

## Spectral Expansion
---
Let $A_{G}$ be the *normalised* adjacency matrix, i.e. all the row sums $=1=$ column sums (doubly stochastic). So instead of $1$ (in an adjacency matrix), the non-zero entries are $\frac{1}{d}$.
Now we can think of $A_{G}$ as a probability distribution.

$A_{G}$ is a real symmetric matrix.
It has *real* eigenvalues $\{ \lambda_{1},\dots,\lambda_{n} \}$, (assume non-increasing order of magnitude) because:
$$
\begin{align*}
Av&=\lambda v\\
v^{T}Av&=v^{T}\lambda v\\
&= \lambda v^{T}v\\
v^{T}Av&= (Av)^{T}v\\
&= \lambda^{T}v^{T}v\\
\implies\lambda^{T}&= \lambda\\
\implies \lambda &\in\mathbb{R}.
\end{align*}
$$
Uniform vector: $u:=\left( \frac{1}{n},\dots, \frac{1}{n} \right)^{T}$

**Obs. 1:** $A_{G}u=u$. $u$ is an eigenvector with eigenvalue $1$.
**Obs. 2:** $\forall i\in[n],\ |\lambda_{i}|\leq 1$.
*Proof:* $A_{G}x=\lambda x$ and let $|x_{j}|$ be the one with the highest value.
$j^{th}$ entry of $\lambda x=\lambda x_{j}$
$j^{th}$ entry of $A_{G}x=\sum\limits_{i}A_{G}[j,i]x_{i}$
So $|x_{j}|\geq |\sum\limits_{i}A_{G}[j,i]x_{i}|=|\lambda||x_{j}|$
$\implies |\lambda|\leq 1$.

**A linear algebraic definition**
$G=(V,E)$ is a $\lambda-$spectral expander if $\lambda_{2}\leq\lambda$. (Makes more sense for a family of expanders, rather than a single graph.) We are interested when $\lambda$ is a constant.

In the normalised adjacency matrix of $G$, $A_{G}$, the second largest eigenvalue is bounded away from the highest (which is 1, because $d-$regular). The difference $1-\lambda$ is called the *spectral gap*.

> [!question] What is the spectral gap of $K_{n}$?
> $A_{K_{n}}= \frac{1}{n-1}J- \frac{1}{n-1}I$.
> $\forall v\perp u,\ Jv=0$. So $J$ will contribute nothing to the other eigenvalues. So $|\lambda_{2}|= \frac{1}{n-1}$.
> $\implies$ spectral gap $= \frac{n-2}{n-1}$.

*Cheeger's Inequality* gives us that the two definitions of an expander, vertex and spectral, are equivalent.

Expanders are also called pseudo-random graphs because of the [[Expander Mixing Lemma]].

---
> [!question] But what does an expander graph look like?

 We have a graph theoretic result:
> [!info] Expander graphs have diameter $O_{\lambda}(\log n)$

How would one prove this?
> [!idea] Using a random walk on an expander, and showing that a random walk *"mixes"* in $O(\log n)$ steps on expanders

**Lemma:**
Let $u=\left( \frac{1}{n},\dots, \frac{1}{n} \right)^{t}$ be the uniform vector.
Let $p$ be any probability distribution on the vertex set $V$ of $G$.
Then for any $r\geq 0$,
$\|A^{T}p-u\|_{2}\leq\lambda^{r}$
$\lambda^{r}\geq \frac{1}{n^{c}} \implies r\geq\Omega(\log n)$
Complete the proof using induction on $r$.
.
.
.

> [!hint] **Lemma:** Given an expander graph, and a small subset $B$ of vertices, a random walk is unlikely to stay confined inside $B$ (we can start anywhere).
> More formally, let $B \subseteq V$ s.t. $|B|=\beta n$, $(0<\beta<1)$, then Prob\[$t-$step $p$ random walk stays inside $B$] $\leq(\beta+\lambda)^{t}\sim 2^{-\Omega(t)}$
> 
> *Proof:* Let $u$ be the uniform distribution.
> Let $P$ be the projector matrix representing the set $B$. $[P_{n\times n}]=P_{ii}=1 \text{ if } i \in B, 0 \text{ otherwise.}$
> $|Pu|$ is the probability that we picked a vector in $B$, this is our first step.
> Then we take a step dictated by the adjacency matrix, and then check the probability that we stay in $B$, which is $|PAPu|$. We continue this.
> Equivalent to showing that $|(PA)^{t}Pu|_{1}\leq(\beta+\lambda)^{t}$.
> The $L_{2}$ norm is easier to calculate than the $L_{1}$ norm.
> > [!info] **Lemma:** $\sqrt{ N } \|(PAP)u\|_{2}\leq(\beta+\lambda)$
> > The idea is to decompose $y=Pu$ into parallel to $u$ and perpendicular to $u$ components. Then the projector matrix will shrink the parallel part and the adjacency matrix will shrink the perpendicular part.
> > 


> [!question] What is the least $\lambda$ can be? In other words, what is the largest spectral gap we can achieve?
> People have constructed "Ramanujan Graphs" with $\lambda= \frac{1}{\sqrt{ D }}$, seems to be the best that can be done.


## Applications
---
[[Error Reduction for RP algorithms]]
[[INW generator for Space Bounded Computation]]
[[Application in Error Correcting Codes]]

---
# References
