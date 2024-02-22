---
tags:
  - Note
  - Incomplete
---
202401121201

Tags : [[Complexity Theory]]
# Co-NP
---
$L\in Co-NP$ iff $\bar{L}\in NP$.

In terms of non det TMs: There is a poly time non det TM $M$ such that $\forall x \in \Sigma^{*}$, $x \in L$ iff $M$ accepts on all computation paths of length $p(|x|)$.

($x \in \bar{L}$ iff there is at least one rejecting computation path of length $p(|x|)$.)

$L\in Co-NP$
- $x \in L\quad\forall y\in\Sigma^{p(|x|)}:R(x,y)$
- $x \in L\quad\exists y\in\Sigma^{p(|x|)}:\lnot R(x,y)$

$R$ is a poly time predicate.

---
**Lemma:** $TAUT=\{ \varphi:\varphi \text{ is a boolean formula that is true for all truth assignments} \}$ is $Co-NP$ complete.
*Proof:* $\varphi \in TAUT$ iff $\lnot \varphi \in \overline{SAT}$.
$\overline{SAT}$ is $Co-NP$ complete.

> [!info] If $TAUT \in NP$, then $NP=Co-NP$!

---
$PRIMES=\{ n:n\text{ is encoded in binary, }n\text{ is prime} \}$
$COMPOSITES=\{ n:n\text{ is encoded in binary, }n\text{ is composite} \}$

**Theorem:** $PRIMES \in NP \cap Co-NP$
*Proof:* $PRIMES \in Co-NP$ because for a composite number we can guess its factors.
A non det polytime algorithm to show that $n$ is prime.
1. Guess the generator element in $(\mathbb{Z}_{n},+,\times)$, $1<a<n$, show $a^{n-1}\equiv 1\mod n$.
2. $\forall j<n-1\quad a^{j}\not\equiv 1 \mod n$
	1. To show this, $\forall p_{i}\quad a^{\frac{n-1}{p_{i}}}\not\equiv 1 \mod n$. Guess all prime factors of $n-1$, there can be at most $\log n$ many factors. Recurse.

$REC-NP-ALGO(n)$;
1. Guess $a \in(1,n)$;
2. Verify $a^{n-1}\equiv 1 \mod n$;
3. Guess $p_{1},p_{2},\dots ,p_{k}\in(1,n)$; $\quad k\leq \log_{2}n$
4. Guess $e_{1},e_{2},\dots,e_{k}\in[1,\log_{2}n]$;
5. Verify $n-1=p_{1}^{e_{1}}p_{2}^{e_{2}}\dots p_{k}^{e_{k}}$, and that $a^{\frac{n-1}{p_{i}}}\not\equiv 1 \mod n\quad 1\leq i\leq k$;
6. for $i:=1$ to $k$
	$REC-NP-ALGO(p_{i})$
7. $ACCEPT$

---
Correctness is fine.
Running time:
$T(n)\leq c\log^{3}n+\sum\limits_{i=1}^{k}T(p_{i})$
**Claim:** $T(n)\leq c'\log^{4}n$
*Proof:* Exercise.

Witness size:
$W(n)\leq c''\log n+\sum\limits_{i=1}^{k}W(p_{i})$
**Claim:** $W(n)\leq c'\log^{2}n$
*Proof:* Exercise.

---
We saw that if an $NP-$complete problem is in $Co-NP$, then $NP=Co-NP$.

$FACTOR=\{ (n,a,b):n,a,b\in \mathbb{N},\text{ encoded in binary}, \exists \text{ a prime factor of }n \text{ in } [a,b] \}$
**Observation:** $FACTOR \in NP$

> [!question] Is $FACTOR \in Co-NP$?
> Yes!
> Guess $p_{1},\dots,p_{k}$;
> Guess primality witnesses for $p_{1},\dots,p_{k}$;
> Find $e_{1},\dots,e_{k}$ s.t. $n=p_{1}^{e_{1}}\dots p_{k}^{e_{k}}$;
> $ACCEPT$ iff none of $p_{1},\dots,p_{k}$ is in $[a,b]$.

$FACTOR\in NP\cap Co-NP$.

> [!warning] If the definition of $FACTOR$ had *a factor* instead of *a prime factor*, the problem would be $NP-$hard, and thus $NP-$complete!

---
If we had $FACTOR$ as an oracle, we could solve integer factorisation in poly-time (in $\log n$, the size of the input).
So given the decision version, we can solve the search version in this case. But we don't know whether Int-Fact is NP-complete??

But for every NP-complete problem, search always reduces to decision.

[[Search vs Decision for NP complete problems]]

---
## Discrete Log problem
$p$ large prime
$g$ is a generator of $\mathbb{Z}_{p}^{*}$
$\forall a\in\{ 1,\dots, \}$

Discrete Log problem is in $NP\cap Co-NP$.

---
# References
[[Complexity Classes]]