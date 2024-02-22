---
tags:
  - Note
  - Incomplete
---
202402091202

Tags : [[Complexity Theory]]
# Quantified Boolean Formulas
---
> [!quote] Arvind
> What is a quantified boolean formula?
> A boolean formula, that's quantified!

We will look at $QBF$s that are completely quantified, and evaluate to true.
$TQBF=\{ \varphi:\varphi \text{ is a true quantified boolean formula} \}$

**Theorem:** $TQBF$ is $PSPACE-$complete under poly-time many-one reductions.

*Proof:* Let $M$ be a $DTM$ that is $n^{c}$ space bounded for some $c>0$.
$L(M)\in PSPACE$.
(a) $TQBF\in PSPACE$
Do a DFS on the possible assignments tree. Stack size in the recursion is $O(|\varphi|^{2})$, $|\varphi|$ many assigned variables, and depth of the tree is $|\varphi|$.

Want to give a polytime reduction $f$ s.t. $x \in L(M)$ iff $f(x)\in TQBF$.
$M$ on input $w$ of length $n$ has $2^{O(n^{c})}$ configurations.

$REACH(I_{0},I_{f},O(n^{c}))$

$REACH(I_{1},I_{2},i)$:
$(\exists\ I')\quad [REACH(I_{1},I',i-1)\land REACH(I',I_{2},i-1)]$
But this makes exponentially many calls to $REACH$. For each midpoint $I'$ it calls $REACH$ twice.

A declarative way of doing the same thing:
$(\exists\ I')(\forall I'')(\forall I''')\quad[(I''=I_{1}\land I'''=I')\lor(I''=I'\land I'''=I_{2})\to REACH(I'',I''',i-1)]$

$|(I''=I_{1}\land I'''=I')\lor(I''=I'\land I'''=I_{2})|=O(n^{c})$



---
# References
