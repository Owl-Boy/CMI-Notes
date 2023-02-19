202302081702

Type : #Note
Tags : [[Topology]]

---
# First Countable space

## Definition:

```ad-note
title:
A space X has a _countable basis at a point_ $x \in X$ if there is a countable collection of open sets $\{B_n\}_{n=1}^{\infty}$ containing $x$ such that each nbhd of $x$ contains at least one of the $B_n's$.

A space X is _first countable_ if it has a countable basis at each point $x \in X$. 
```

#### Note: every metric space is first countable.

## Sequence Lemma:

```ad-note
title:
Let X be a topo space, $A \subset X, x \in X$.
1) If there is a sequence $(x_n)_{n=1}^{\infty}$ of points in A that converge to x, then $x \in Cl(A)$
2) If X is metrizable (first countable) and $x \in Cl(A)$ then there is a sequence of points $x_n \in A$ such that $x_n \to x$.
```
#### Proof:
1) Suppose not, then there is a nhbd of $x$ that is completely outside A and so the points $x_n$ cannot converge to $x$, contradiction.
2) First note that $x \in Cl(A) \implies$ every nbhd of $x$ intersects A. Just take $x_n$ to be a point in $\bigcap \limits_{i=1}^{n} B_i$ other than $x$, and this gives a sequence converging to $x$.

## Lemma:

```ad-note
title:
Let $f:X \to Y$ be a function.
1) If f is cts, then for all convergent sequences $x_n \to x$, $f(x_n) \to f(x)$.
2) If X is metrizable (first ctble) and for all convergent sequences $x_n \to x$, $f(x_n) \to f(x)$, then f is cts.
```
#### Proof:
1) Take an open nbhd V of f(x), then $U = f^{-1}(V)$ contains all $x_n$ for all $n \ge n_0$ for some $n_0$, and so $V$ contains all $f(x_n)$ for $n \ge n_0$.
2) Need to show that $f(Cl(A)) \subseteq Cl(f(A))$. Let $x \in Cl(A)$, then since X is first countable, there is a sequence $x_n \to x$ and so $f(x_n) \to f(x)$ and thus $f(x) \in Cl(f(A))$. 

---
# Related Problems

---
# References
[[Closure and Interior and Limit Points]]
[[Continuous Functions]]
