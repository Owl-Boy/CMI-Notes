---
tags:
  - Note
  - Incomplete
---
202309211509

Tags : [[Algorithmic Coding Theory]]

---
# List decoding RS codes up to the Johnson radius

## Toy case 1:
2 unknown polynomials $P_1(x)$, $P_2(x)$ of degree $k<\frac n2$.
We are given $(a_i,b_i)$ s.t. $a_i = P_1(\alpha_i), b_i = P_2(\alpha_i)$, or $a_i = P_2(\alpha_i), b_i = P_1(\alpha_i)$.

Basically we have two polynomials, and their evaluations on some points, but for each pair, we don't know which of $P_1$ and $P_2$ each came from.

We can get the sum polynomial $P_1+P_2$, and the product polynomial $P_1P_2$, and get $P_1-P_2$, and get back the original polynomials in some order either directly or by using fanciness such as 'auxiliary bivariate polynomial', _Hensel's lifting lemma_.

**Auxiliary bivariate polynomial** is just $f(X,Y) = (Y-P_1(x))(Y-P_2(x))$.
Then you factor this into irreducible polynomials which can be done in poly time.


## Toy case 2:
2 unknown polynomials $P_1(x)$, $P_2(x)$ of degree $k<\frac n6$.
We have one evaluation for each of $n$ points $\alpha_1, \dots, \alpha_n$, but we don't know which polynomial was evaluated at what point. We are told, however, that both the polynomials were evaluated at at least one-third of the points.

---

## Pattern matching

All these algorithms - Berlekamp-Welch, Sudan, Guruswami-Sudan, have the following two step structure:
**Step 1 (Interpolation step):** Find non zero $Q(X,Y)$ st $Q(\alpha_i, y_i)=0$
**Step 2 (Root finding):** If $Y-P(X)$ is a factor of $Q(X,Y)$ then output $P(X)$.

The first step seems to be the creative one.

In general, we try to prove a polynomial is zero, by saying it has degree at most say $d$, but vanishes at $>d$ points.

---
## Algorithm 1
**Input:** $n \geq k \geq 1$,
		$e = n-t$, $l \geq 1$.
		$n$ pairs $\{(\alpha_i, y_i)\}$
**Output:** List of polynomials $P(X)$ of degree at most $k-1$. (can be empty)

### Interpolation step
1. Find a non zero $Q(X,Y)$ st $\deg_X(Q) \leq l$, $\deg_Y(Q) \leq \frac nl$, st $Q(\alpha_i, y_i)=0, 1 \leq i \leq n$
2. $\mathbb{L} \leftarrow \phi$
3. Add $P(X)$ to $\mathbb{L}$ under some conditions*

Prove correctness of Step 1.

There's nothing more to do in list decoding of RS codes. Johnson bound is the best thing we can do. Sudan had found an algorithm upto $(1-\sqrt{R})$, and then Guruswami-Sudan made it better $(1-2\sqrt{R})$.


---
# References

https://people.eecs.berkeley.edu/~venkatg/pubs/papers/listdecoding-NOW.pdf
[[Guruswami-Sudan's list decoding of RS codes]]
[[Reed-Solomon Codes]]
[[Johnson bound]]