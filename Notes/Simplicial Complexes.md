---
tags:
  - Note
  - Incomplete
---
202403141403

Tags : [[Expander Graphs and Applications]]
# Simplicial Complexes
---
$[n]=\{ 1,2,\dots,n \}$ ground set
SC: $X$ is a downward closed set family over $2^{[n]}$, i.e. if $\sigma \in X, \tau \in X\implies \tau \in X$.
$X=\{ \sigma \}$, $\sigma$ are called *faces* in Linear Programming, and *simplices* (pl. for *simplex*) in Topology.

$dim(\sigma):=|\sigma|$, $dim(\phi)=0$.
Given integer $k$, $X(k):=\{ \sigma \in X:dim(\sigma)=k \}$.
$dim(X):=max\{ k:X(k)\neq \phi \}$.

$X$ is said to be **pure** if each maximal $\sigma$ has dimension equal to $dim(X)$.

**Link** of $\tau$: $X_{\tau}=\{ \sigma\setminus \tau:\sigma \in X,\tau \subset \sigma \}$
**Exercise:** $X_{\tau}$ is a simplicial complex of dimension $d-k$.

weight $w:X\to \mathbb{R}_{>0}$
$X$ is said to be **balanced** if $w(\sigma) \in X(d)=\sum\limits_{dim(\tau)=d+1,\sigma \subset \tau}w(\tau)$.

> [!danger] We will assume all SCs to be pure and balanced, unless stated otherwise.

Inspired by Graph Theory, we call $X(1)$ vertices, and $X(2)$ edges, and $((X(1),X(2))$ a *skeleton* of the SC.

## Walks on Simplicial Complexes
---
We define two kinds of walks (between $X(k)$ and $X(k+1)$): $p_{k}^{\land}$, and $p_{k+1}^{\lor}$.

$p_{k}^{\land}:$
- start from a $\tau \in X(k)$
- pick a neighbour $\eta$ in $X(k+1)$ with probability proportional to $w(\eta)$
- from $\eta$ delete one of the elements u.a.r. to arrive at $\sigma\in X(k)$.
$\tau,\sigma\in X(k):$
$$
p_{k}^{\land}(\tau,\sigma)=\left\{
\begin{align*}
\sum\limits_{\tau \subset\eta,\eta \in X(k+1)} \frac{w(\eta)}{w(\tau)}. \frac{1}{k+1}= \frac{1}{k+1} &&\tau=\sigma\\
\frac{w(\tau \cup \sigma)}{w(\tau)}. \frac{1}{k+1} && \tau\neq \sigma\\

\end{align*}
\right.
$$

$p_{k}^{\lor}:$
- start from a $\tau \in X(k+1)$
- delete one of the elements u.a.r. to arrive at $\eta \in X(k)$
- pick a neighbour of $\eta$ with probability proportional to its weight, arrive at $\sigma \in X(k+1)$.
$\tau,\sigma\in X(k):$
$$
p_{k+1}^{\lor}(\tau,\sigma)=\left\{
\begin{align*}
\sum\limits_{\eta \subset \tau,\eta \in X(k)} \frac{w(\tau)}{w(\eta)}. \frac{1}{k+1} &&\tau=\sigma\\
\frac{w(\sigma)}{w(\sigma \cap \tau)}. \frac{1}{k+1} && \tau\neq \sigma\\
\end{align*}
\right.
$$


$p_{k}^{\land}$ for $k=1$, $p_{1}^{\land}= \frac{1}{2}I+ \frac{1}{2} \tilde{p}_{1}^{\land}$, where $\tilde{p}_{1}^{\land}$ is called the non lazy walk.

**Definition:** A pure $d-$dimensional weighted complex $(X,w)$ is $\lambda-$*local spectral expander* if $\lambda_{2}(\tilde{p}_{\tau_{1}}^{\land})\leq\lambda$ $\forall \tau \in X$.

[Kauffman-Oppenheim, '18]
**Theorem:** Suppose $(X,w)$ is a $0-$local spectral expander. Then $p_{k}^{\land}$ has at most $|X(i)|$ eigenvalues of order $> 1- \frac{i+1}{k+1}$ for $-1\leq i\leq k$. (We define $X(-1)=\phi$.)

*Proof:*
> [!example] $A \preccurlyeq B$ is notation for $B-A$ is positive semidefinite.


> [!lemma] Key Lemma:
> $p_{k}^{\land}\preccurlyeq \frac{k}{k+1}p_{k}^{\lor}+ \frac{1}{k+1}I$
> In other words, $M=p_{k}^{\land}-\left( \frac{k}{k+1}p_{k}^{\lor}+ \frac{1}{k+1}I \right)$ is Negative Semi Definite.
> *Proof:*
 $$
 M(\tau,\sigma)=\left\{
 \begin{align*}
 \frac{1}{k+1}\frac{w(\tau \cup \sigma)}{w(\tau)} - \frac{1}{k+1} \frac{w(\sigma)}{w(\sigma \cap \tau)}&&\tau\neq \sigma \\
 -\frac{1}{k+1}\sum\limits_{\eta \subset \tau} \left( \frac{w(\tau)}{w(\eta)} \right) &&\tau=\sigma
 \end{align*}
 \right.
 $$
 
 

> *Claim:*
> $$
> M_{\eta}(\tau,\sigma)=\left\{
> \begin{align}
 M(\tau,\sigma)\\
\end{align}
> \right.
  $$
 

Assuming the key lemma, the proof of the theorem follows by induction on $k$.
inductionnnnn












---
# References
