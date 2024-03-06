---
tags:
  - Note
  - Incomplete
---
202402021202

Tags : [[Complexity Theory]]
# Time and Space Hierarchy Theorems
---
> [!quote] If we have more time we can do more. If we have more space we can do more.

Read up **Linear Speed-up Theorem** from Hopcroft-Ullman, there's one page. Also **Space Compression Theorem**. (Chapter 12)

$DSPACE(S(n)):$ Languages accepted by $DTM$s with a read-only input tape and one or more $S(n)-$space bounded worktapes. (Because we would typically want to talk about sublinear $S(n)$, but the input itself is linear.)

$NSPACE(S(n))$ is defined similarly.

## Time Hierarchy Theorem (dream version)
---
- $O(T_{1}(n))<O(T_{2}(n))\implies DTIME(T_{1}(n))\subsetneq DTIME(T_{2}(n))$.
But the *Linear Speed-up Theorem* tells us that if $\frac{T(n)}{n}\to \infty$ then $\forall c>0$, $DTIME(T(n))=DTIME(cT(n))$.
So this is not enough! :(
What about $\lim\limits_{n\to \infty} \frac{T_{1}(n)}{T_{2}(n)}=0$?
- But diagonalisation reasons (????) So $\lim\limits_{n\to \infty} \frac{T_{1}^{2}(n)}{T_{2}(n)}=0$? This gives "easy diagonalisation".

## Deterministic Time Hierarchy Theorem
if $\lim\limits_{n\to \infty} \frac{T_{1}(n)\log T_{1}(n)}{T_{2}(n)}=0$, then $DTIME(T_{1}(n))\subsetneq DTIME(T_{2}(n))$.

---
A function $T(n):\mathbb{N}\to \mathbb{N}$ is called *time-constructible* if there is a $DTM$ $M$ that is $T(n)$ time bounded and for every $n$ there exists an input of length $n$ s.t. $M$ takes exactly $T(n)$ steps on it.
*Fully time-constructible:* $T(n)$ is fully time-constructible if there exists a $DTM$ $M$ s.t. $\forall n$ and for all inputs of length $n$ $M$ takes exactly $T(n)$ steps.
*Space-constructible:* $S(n)$ is space constructible if there is an $S(n)$ space bounded $DTM$ $M$ that uses exactly $S(n)$ worktape cells for some input.

[[Non deterministic Time Hierarchy Theorem]]
[[Non deterministic Space Hierarchy Theorem]]
## Deterministic Space Hierarchy Theorem
if $\lim\limits_{n\to \infty} \frac{S_{1}(n)}{S_{2}(n)}=0$ and $S_{2}(n)$ is fully space constructible ($S_{2}(n)\geq\log n$) then $DSPACE(S_{1}(n))\subsetneq DSPACE(S_{2}(n))$.

---
*Proof:* We need to construct $L$ that is in $DSPACE(S_{2}(n))$ but $L\not\in DSPACE(S_{1}(n))$.
Input $w$:
1. Mark off $S_{2}(|w|)$ work tape region. Can do it in $S_{2}(|w|)$ space as it is fully space-constructible.
2. Simulate $M_{w}$ on $w$ within $S_{2}(|w|)$ space.
If it attempts to leave the marked space, just reject and stop.
Otherwise, set up a counter to count the number of configurations of $M_{w}$:
For the counter we need space equal to $\log((n+1).c^{S_{2}(|w|)}.S_{2}(|w|).c)$ (This is where we require $S_{2}(n)\geq \log n$.)
3. If $M_{w}$ completes the simulation on $w$, then diagonalise.


---
# References
[Hopcroft-Ullman, Chapter 12]