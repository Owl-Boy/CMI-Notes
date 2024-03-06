---
tags:
  - Note
  - Incomplete
---
202402231202

Tags : [[Complexity Theory]]
# Non deterministic Time Hierarchy (Zak's Theorem)
---
$T(n)$ is fully time constructible. $\lim\limits_{n\to \infty} \frac{t(n+1)}{T(n)}=0$, then $NTIME(t(n))\subsetneq NTIME(T(n))$.
*Proof:* By diagonalisation we'll construct an $NTIME(T(n))$ machine s.t. $L(N)$ is not in $NTIME(t(n))$.

> [!bug] We don't know anything about $t(n)$, how do we diagonalise against all machines that run in time $t(n)$?
> We don't worry about $t(n)$, and we just simulate the machine till time $T(n)$, like we did in the deterministic case. The catch is, although the original machine might run for time $t(n)$, when we simulate it, it's gonna take longer, but less than $T(n)$, so it's okay. (It won't always be less than $T(n)$, but eventually it will, which is why the limit.)

Can we simulate $T(n)$ time bounded $k-$tape $NTM$s by a $5-$tape $NTM$ in $O(k.T(n))$ time?
Yes.
1. Guess the $T(n)$ many non det moves that $M$ makes on input $x$.
2. For $1\leq i\leq k$, $M'$ checks that the above guess is consistent with $M'$s moves on tape $i$.
By induction we can check that step 2. implies that $M$ has a run consistent with the guessed non det moves.

### Diagonalisation
---
Enumerate all $5-$tape $NTM$s $M_{1},M_{2},\dots$ . Consider inputs of the form $1^{i}01^{m}01^{k}$, ignore everything else.

Description of $NTM$ $N$:

1. If $k<i^{T(i+m+2)}$, then simulate $M_{i}$ on $1^{i}01^{m}01^{k+1}$ and accept iff $M_{i}$ accepts.
2. If $k=i^{T(i+m+2)}$, then deterministically simulate $M_{i}$ on $1^{i}01^{m}0$ (using a $T(n)$ clock).
$L(N)\in NTIME(T(n))$
Claim: $L(N)\not\in NTIME(t(n))$
Proof:
Suppose not. Let $M_{i}$ be an $NTIME(t(n))$ machine s.t. $L(M_{i})=L(N)$.
$\lim_\limits{ n \to \infty } \frac{t(n+1)}{T(n)}=0$ gives that for large enough $m$, $t(i+m+3+k)<T(i+m+2+k)$, and $i^{T(i+m+2)}\leq T(i+m+i^{T(i+m+2)}+2)$.
Diagonalisation step:
$1^{i}01^{m}0\in L(N)\iff1^{i}01^{m}01\in L(M_{i})$,
$1^{i}01^{m}01\in L(N)\iff1^{i}01^{m}01^{2}\in L(M_{i})$,
.
.
.
$1^{i}01^{m}01^{i^{T(i+m+2)}}\in L(N)\iff1^{i}01^{m}0\not\in L(M_{i})$.

So at some point something must be not equal (??)



---
# References
[[Time and Space Hierarchy Theorems]]
[Lance Fortnow's blog, 2004]