---
tags:
  - Note
  - Incomplete
---
202402091302

Tags : [[Complexity Theory]]
# Polynomial-Time Hierarchy
---
$L\in\Sigma_{2}^{P}$ if there is a polytime computable predicate $R(x,y,z)$ and a polynomial $p(n)$ s.t. $\forall x \in\Sigma^{*}$
$x \in L\iff(\exists\ y: |y|\leq p(x))$, $(\forall\ z: |z|\leq p(x))\ R(x,y,z)$.

More generally,
$L\in\Sigma_{i}^{P}$ if there is a polytime $(i+1)-$ary predicate $R(x,y_{1},\dots,y_{i})$ and a polynomial $p(n)$ s.t. $\forall x \in\Sigma^{*}$
$x \in L\iff(\exists\ y_{1})(\forall\ y_{2})\dots(Qy_{i})\ R(x,y_{1},\dots,y_{i})$, $|y_{j}|\leq p(|x|)$.

$L\in\Pi_{i}^{P}$ iff $L^{C}\in\Sigma_{i}^{P}$, i.e.
$x \in L\iff(\forall y_{1})(\exists y_{2})\dots(Q'y_{i})\ R(x,y_{1},\dots ,y_{i})$, $|y_{j}|\leq p(|x|)$.

---
**Exercise:** $\Sigma_{i}^{P}\subseteq PSPACE$.

$PH=\bigcup\limits_{i\geq 0}\Sigma_{i}^{P}=\bigcup\limits_{i\geq 0}\Pi_{i}^{P}$.

**Lemma:** $PH=PSPACE\implies PH=\Sigma_{i}^{P}$ for some $i$, $\implies\Sigma_{i}^{P}\cap\Pi_{i}^{P}$.
*Proof:*
Because $\Sigma_{i}^{P}$ is closed under polytime many-one reductions,
(**Exercise:**) $L_{1}\leq_{m}^{P},\ L_{2}\in\Sigma_{i}^{P}\implies L_{1}\in\Sigma_{i}^{P}$.
We know $TQBF$ is $PSPACE-$complete.
$PH=PSPACE\implies TQBF\in PH=\bigcup\limits_{i\geq 0}\Sigma_{i}^{P}$
$\implies TQBF\in\Sigma_{k}^{P}$,
$\implies PSPACE\subseteq\Sigma_{k}^{P}$.

## Oracle definition of $PH$
---
$\Sigma_{2}^{P}=NP^{NP}=\bigcup\limits_{A\in NP}NP^{A}=NP^{SAT}$.
This is equivalent to $\Sigma_{2}^{P}\subseteq NP^{NP}$ and $NP^{SAT}\subseteq\Sigma_{2}^{P}$.

$L\in\Sigma_{2}^{P}$ if $\forall x$, $x \in L\iff(\exists y_{1})(\forall y_{2})\ R(x,y_{1},y_{2})$.
Using the oracle $B=\{\langle x,y_{1} \rangle:|y_{1}|\leq p(|x|), \forall y_{2}\ R(x,y_{1},y_{2}) \}$, $(\forall y_{2}\ R(x,y_{1},y_{2}))\in co-NP$,
we get that $L\in NP^{NP}$.
(This is just: non deterministically guess $y_{1}$, and then use the oracle to check $R(x,y_{1},y_{2})$ for all $y_{2}$.)

For the other direction, we look at the computation tree, guess the answer of the oracle at each query made, (don't actually query it), and at the end we reach some accepting state (all other paths we ignore). Now we just want to verify that our guesses are correct, which means we want to check that some of the $q_{i}$'s are in $SAT$, and the others are not, along the path. But these are only so many (unlike a universal quantifier), so we need to check whether the AND of all of the YES-guessed queries is in $SAT$, and the OR of all the others is not in $SAT$. But this is just another $SAT$ formula (two formulas, one for each) which we can do using 








---
# References
