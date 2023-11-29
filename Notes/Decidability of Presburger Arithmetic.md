---
tags:
  - Note
---
202311282111

Tags : [[Logic]]
# Decidability of Presburger Arithmetic
---
>[!note] Theorem
> The theory of structure $\mathfrak N_{\mathcal A}=\{\mathbb N; 0,S,<, +\}$ is *decidable*.

The proof is based on [[Quanitifier Elimination for Natural Numbers With Successor#^411d8b|quantifier elimination]].
$\mathfrak N_{A}$ itself does not admit *quantifier elimination* so we look at the following arithmetic
$$
\mathfrak N^\equiv = (\mathbb N; 0, S,<, +,\equiv_{2},\equiv_{3},\dots)
$$
Where $\equiv_{k}$ represents the binary relation of congruence modulo $k$.
Every statement in $\mathfrak N_A$ is also a statement in $\mathfrak N^\equiv$, and the latter admits *quantifier elimination*.

>[!hint]
>We know that $\mathfrak N^\equiv$ is a superset of $\mathfrak N_A$ so every formula in $\mathfrak N_A$ is also a formula in $\mathfrak N^\equiv$.

## Structure
### Terms
We assume all terms to be of the form 
$$
S^n(\mathbf{0})+ n_{1}x_{1} +\dots + n_{k}x_{k}
$$
This is obvious from the axioms
- $S(\varphi + \psi)\to S(\varphi) + \psi$
- $S(\varphi)+\psi\to\varphi+S(\psi)$

### Formulae
All formule are of the disjunctions of $\exists y(\beta_{1}\land \beta_{2}\dots \beta_{n})$ where $\beta_i$ is an atomic formula.

## Quantifier Elimination Algorithm

### Plan
- We remove negations
- Then we simplify the definitions by removing coefficients of the variable
- We deal with the special case where congruence is one of the atomic formulas
- We deal with the general case, without congruences
### Removing Negations
- $\lnot(t_1 \equiv t_2)$ becomes $(t_{1}<t_{2})\lor(t_{2}<t_{1})$, something similar for $\lnot (t_{1}<t_{2})$ and $\lnot (t_{2}<t_{1})$
- $\lnot(t_{1}\equiv_{k}t_{2})$ becomes $(t_{1} \equiv_{k} t_{2}+S(\mathbf{0} ))\land(t_{1} \equiv_{k} t_{2}+S^2(\mathbf{0} ))\land\dots \land(t_{1} \equiv_{k} t_{2}+S^{k-1}(\mathbf{0} ))$ 

we then regroup them into *DNF*.

Now we have a disjunction of formulas of the form $\exists y (\alpha_1\land\dots\land \alpha_m)$ where each $\alpha_i$ has one the following forms(the second way of writing is just syntactic sugar)
- $ny+t=u$ 
- $ny+t\equiv_m u$
- $ny+t<u$
- $u<ny+t$
which can be written as 
- $ny=u-t$
- $ny\equiv_{k}u-t$
- $ny<u-t$
- $u-t<ny$

### Uniformizing Coefficients of $y$
Say one of the parts of the formula is 
$$
\exists y(w<4y\land 2y<u\land 3y<v\land y\equiv_{3}t)
$$
We use the fact that
- $a<b$ is true iff $ka<kb$ 
- $a\equiv_{k}b$ is true iff $ma\equiv_{mk}mb$
and we get 
$$
\exists y(3w<12y \land 12y<6u \land  12y < 4v \land 12y \equiv_{36} 12t)
$$
We now simplify the above formula by saying that there is some number that can be put in place of $12y$ and the number is divisible by $12$.
$$
\exists x(3w<x \land x < 6u \land x<4v \land x\equiv_{36} 12t\land x\equiv_{12}\mathbf{0})
$$

### Dealing with Equality 
This is a special case that can be dealt easily
If one of the atomic formulas is an equality of the form $x+y\equiv u$ then we can replace $\exists x \theta$ with $\theta[x := u-t] \land u > t$ 

We assume the formula does not contain $\equiv$ for the last section.

### Quantifier elimination where $\equiv$ is not in the formula
Since we have eliminated negation, and assuming our formulas do not contain $\equiv$, we assume that our formula is the disjunction of subformulas of the form 
$$
\exists x \left[
  \left(\bigwedge_{i\in[1..l]} r_{i}-s_{i}<x\right)\land
  \left(\bigwedge_{i\in[1..m]} x < t_{i}-u_{i}\right) \land
  \left(\bigwedge_{i\in[1..n]} x\equiv_{m_{i}} v_{i}-w_{i}\right)
\right]
$$

#### Without Congruencies
>[!tip] Intuition
>If there are no congruencies
>The first chunk is a bunch of lower bounds
>The second chunk is a bunch of upper bounds
>So we just need to check if the smallest upper bound is atleast 2 more the largest lower bound, But since we do not have a max operator, we just compare every upper bound-lower bound pair.
>We also need to make sure that upper bounds are at least 1


The first two chunks together can be converted to 
$$
\bigwedge_{i<k}\bigwedge_{j<l}\Big(\mathbf{S}(r_{j}-s_{j})<t_{i}-u_{i}\Big)\land\bigwedge_{i<k}\Big(\mathbf{0}<t_{i}-u_{i}\Big)
$$
#### With Congruencies
Congruencies force us to manually check for existance of such an $x$, but they also restrict the search space to modulo classes, hence making it finite.

Given all $m$ such that there is an atomic formula like $x\equiv_{m}v_{i}-w_{i}$, let $M$ be the least common multiple of all such $m$.

Then all modulo operators are together periodic with periodicity $M$, we should just check the first $M$ numbers starting after the biggest lower bound, which we again test by checking $M$ numbers after each lower bound, so we get the following

$$
\begin{align}
\bigvee_{j<l}\bigvee_{1\leq q\leq M}\Big[\quad
  &\bigwedge_{i<l} r_{i}-s_{i} < (r_{j}-s_{j}+\mathbf{S}^q\mathbf{0})\quad \land\\
  &\bigwedge_{i<m} (r_{j}-s_{j}+\mathbf{S}^q \mathbf{0}) < t_{i}-u_{i}\quad \land \\
  &\bigwedge_{i<n} (r_{j}-s_{j}+\mathbf{S}^q\mathbf{0})\equiv_{k_{i}} v_{i}-w_{i}\quad
\Big]
\end{align}
$$

---
# References
[[First Order Logic]]