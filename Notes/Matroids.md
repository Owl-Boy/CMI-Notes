---
tags:
  - Note
  - Incomplete
---
202403081403

Tags : [[Combinatorial Optimisation]]
# Matroids (Whitney 1935)
---
A matroid $M$ has a ground set $E$, a collection $I$ of subsets of $E$, called independent sets, i.e. $M=(I,E)$ s.t.
1. *Downward closure:* If $Y\in I$, then $\forall X\subseteq Y, X \in Y$.
2. *Extension:* If $X,Y\in I, |X|<|Y|$ then $\exists e\in Y\setminus X$ s.t. $X\cup \{ e \}\in I$.

## Examples
---
### Uniform matroid $U_{k,n}$
$I=\{ X\subseteq E\mid |X|\leq k \}$ for a given $k$.
$U_{n,n}$ is known as the *free matroid*.

### Partition matroid
$E=E_{1}\dot{\cup}E_{2}\dot{\cup}\dots \dot{\cup}E_{l}$
$E_{1},\dots,E_{l}$ is a partition of $E$.
Integers $k_{1},\dots ,k_{l}$ as input.
$I=\{ X\subseteq \mid |X\cap E_{i}|\leq k_{i}, i\in[l] \}$

> [!note] Observe that if the sets overlap, then $I$ is not a matroid because we can have $|X|<|Y|$, but $X$ could have all the constraints tight as one element can then contribute to multiple constraints.

### Linear matroid
Matrix $A_{m\times n}$, columns $A_{1},\dots,A_{n}$.
$I=\{ X\subseteq[n]\mid \text{Colums corresponding to }X\text{ are linearly independent} \}$
The matrices could be over $\mathbb{F}_{2}$ or $\mathbb{F}_{3}$.

## Representable matroids
---
A matroid with which we can associate a linear matroid.
eg. $U_{2,3}$ can be represented as:
$$
A=\begin{bmatrix}
1 & 1 & 0 \\
1 & 0 & 1 \\
0 & 1 & 1
\end{bmatrix}
$$
> [!attention] Claim: $U_{2,4}$ is not representable over $\mathbb{F}_{2}$ but representable over $\mathbb{F}_{3}$. (Prove.)

---
Is this a matroid?
$E=$ edges of a graph
$I=\{ F\subseteq E\mid F\text{ is a matching} \}$
No, because maximal (but not maximum) matchings exist, which can not be extended to a specific maximum matching.

### Graphic matroid/cycle matroid
What about this?
$I=\{ F\subseteq E\mid \text{There is no cycle in }F\text{ (i.e. }F\text{ is a forest).} \}$
Yes.
One proof is by looking at the incidence matrix and prove the following
> [!attention] Claim: A subset of columns is linearly independent iff the corresponding edges don't contain a cycle.

Another proof is by observing that a forest with more edges will have less connected components.

**Obs.:** A maximal independent set in a matroid is also a maximum independent set. So all maximal independent sets have the same size.
A maximal independent set in a matroid is called a *Base*.
eg. for the graphic matroid, a base is the set of spanning trees (or spanning forests if the graph is disconnected).

**Regular matroids** are precisely those matroids that can be represented over $\mathbb{R}$ by a TUM matrix. 
Graphic matroids are representable over any field (put 1 and -1 in the incidence matrix), and hence regular.

### Matching matroid
Ground set $V$
$I=\{ S\subseteq V\mid \exists \text{ a matching that matches all vertices in }S \}$

---
**Circuit** is defined as a minimal dependent set $C$. That is, $C$ itself is not independent, but $\forall e\in C$, $C\setminus \{ e \}$ is an independent set.

> [!Lemma] Let $S\in I$, $S$ maximal, let $S\cup \{ e \}\not\in I$. Then there is a unique circuit $C\subseteq S\cup \{ e \}$.
> 
> > [!tip] Think of the spanning tree example. There is only one cycle that forms after we add another edge.
> 
> *Proof:* Let $C_{1},C_{2}$ be circuits $\subseteq S\cup \{ e \}$.
> Let $f\in C_{1}\setminus C_{2}$.
> $C_{2}\subseteq (S\cup \{ e \})\setminus \{ f \}$
> But by definition of a circuit, $C_{1}\setminus \{ f \}$ must be an independent set.
> $e\in C_{1}$ because $C_{1}$ was formed due to addition of $e$.
> Now this can be extended to an independent set by adding elements from $S$, till this extended set $X$ becomes the same size as $S$. In this process we can never add $f$, because that would recreate $C_{1}$, which is not independent.
> We end up with $|X|=|S|$, and $C_{2}\subseteq X$, where $C_{2}$ is a circuit sitting inside $X$, which is independent. Contradiction!


---
# References
