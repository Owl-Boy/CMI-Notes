---
tags:
  - Note
  - Incomplete
---
202403151403

Tags : [[Combinatorial Optimisation]]
# Max wt base of a matroid
---
$M=(E,I)$, $w:E\to \mathbb{R}$, $E=\{ 1,\dots,n \}$
$w(S)=\sum\limits_{i \in S}w(i)\quad \forall S\subseteq E$
Let $w(1)\geq\dots\geq w(n)$.

$S=\phi$, $I=\{ S \}$
for $i=1$ to $n$:
	if $S+i\in I$ then $S\leftarrow S+i$
end for
Return $S$.

**Theorem:** Algo outputs a max wt base iff $M$ is a matroid.
*Proof:*

(1) Let $M$ be a matroid. We prove that the greedy algo works.
Induction on $i$.
*To prove:* $(\star)$ At any iteration $i$, $\exists$ a max wt base $B_{i}$ s.t. $S_{i}\subseteq B_{i}$, and $B_{i}\setminus S_{i}\subseteq \{ i+1,\dots,n \}$.
Base case: $S=\phi$, trivial.
Assume $(\star)$ up to $i-1$ iterations.
$S_{i-1}\subseteq B_{i-1}$, $B_{i-1}$ is a max wt base, $B_{i-1}\setminus S_{i-1}\subseteq \{ i ,\dots,n \}$.
1. If $i \in B_{i-1}$ then $S_{i-1}+i\subseteq B_{i-1}$.
So $S_{i-1}+i$ is independent.
$B_{i}=B_{i-1}$, $S_{i}=S_{i-1}+i$, $B_{i}\setminus S_{i}\subseteq \{ i+1,\dots,n \}$.
2. $i\notin B_{i-1}$ and $S_{i-1}+i\notin I$
$S_{i}=S_{i-1}$, $B_{i}=B_{i-1}$ according to our algorithm.
3. $i\notin B_{i-1}$, but $S_{i-1}+1\in I$.
$S_{i}=S_{i-1}+i$
If $|S_{i}|<|B_{i-1}|$, (else $B'=S_{i}$)
then $\exists\ j\in B_{i-1}$ s.t. $S_{i}+j\in I$.
Let $B'$ be obtained by adding elements other than $j$ from $B_{i-1}$ to $S_{i}$.
$B'=B_{i-1}-j+i$, $|B'|=B_{i-1}$.
$w(B')=w(B_{i-1})-w(j)+w(i)$.
But $j>i$, so $w(j)\leq w(i)$, so $w(B_{i-1})\leq w(B')$.
But $B_{i-1}$ is a max wt base, so $B'$ is also a max wt. base.
So we can set $B_{i}=B'$.

(2) Assume $M$ is not a matroid.
*Goal:* Exhibit a $w: E\to \mathbb{R}$ s.t. the algo does not give a max wt base.

Case 1.:
$M$ is not downward closed.
Let $T\in I$ but $S\subset T$, $S\notin I$.
$$
w(i)=\left\{
\begin{align}
2 && i\in S \\
1 && i\in T\setminus S \\
0 && \text{otherwise}
\end{align}
\right.
$$
$w(T)\geq |T|$.
max wt set $=T$
Our algo picks wt $2$ elements, but it can't pick $S$, so it will leave something out of $S$ since $S\notin I$. So the algo can't pick $T$ and hence fails.

Case 2.:
$M$ violates extension property.
$\exists S,T\in I$, $|S|<|T|$ but $\forall i \in T\setminus S$, $S+i\notin I$.
$$
w(i)=\left\{
\begin{align}
1+\epsilon &&i\in S \\
1&&i\in T\setminus S \\
0&&\text{otherwise}
\end{align}
\right.
$$
Our algo first picks $S$.
Now it has to pick some $i\in E\setminus T$ to get $S'$.
$w(S')=(1+\epsilon)|S|$
We can pick $\epsilon$ s.t. $(1+\epsilon)|S|<|T|$















---
# References
