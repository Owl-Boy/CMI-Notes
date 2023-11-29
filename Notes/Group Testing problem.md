---
tags:
  - Note
  - Incomplete
---
202311141511

Tags : [[Algorithmic Coding Theory]]

---
# Group Testing problem

```ad-tip
title: Problem
There are $N$ people, $n$ have some disease, say CoViD. We want to test the people for the disease, and the tests are costly. $n\ll N$. The naive way would be to draw a sample from each of them, and test each sample separately, which is costly.
So another way to approach this is *'pooled testing'*, i.e. you pool samples together, and test them in groups.
```

**Input:** # individuals $N$, $x_{1},x_{2},\dots,x_{N}$
upper bound on the number of infected individuals $d$
**Query/test:** arbitrary subset of $[N]$
$$
A(S)=\left\{
\begin{align*}
1 &&\text{iff }\sum\limits_{i\in S}x_{i}\ne 0\\
0 &&\text{otherwise.}
\end{align*}
\right.
$$
**Goal:** minimise the number of queries

*Adaptive approach:* $t^{a}(d,N)$ If a subset gives 0 on querying, we don't test it again (??)
*Non-adaptive approach:* $t(d,N)$ Pre-determined queries. Represent the set of tests as a matrix.
$1\leq t^{a}(d,N)\leq t(d,N)\leq N$

We have the bounds for $1\leq d\leq N$,
$t^{a}(d,N)\geq d\log \frac{N}{d}$
$t(1,N)\leq \lceil \log(N+1)\rceil$

---
$M_{t\times N}:$ binary matrix
$M_{i}=\{ j\ |\ m_{ij}=1 \}:$ $i^{th}$ pool
$M^{j}=\{ i\ |\ m_{ij}=1 \}:$ set of pools that $j$ belongs to

$M_{t\times N}x_{N\times1}=y_{t\times1}$ (test outcome vector)
$y=\bigcup\limits_{j\in D}M^{j}$
We want to uniquely identify $D$.

*'Separable matrix:'* A $t\times N$ binary matrix $M$ is $d-$separable if the unions of upto $d$ columns are all distinct.

$M$ is a $d-$separable $t\times N$ matrix, then time is something I didn't see.

**Decoding:** Identifying the positives given the test outcome vector.

*Disjunct matrix:* A $t\times N$ binary matrix $M$ is said to be $d-$disjunct if the union of arbitrary $\leq d$ columns does not contain another column.

$(d+1)-$separable $\implies\ d-$disjunct $\implies\ d-$separable

So the following algorithm works!

```ad-success
title: Naive decoding algorithm

```python
for j = 1 to N
	if item j belongs to at least one negative test, then mark j as a negative item.
	end if
end for
return R(the remaining items)
```


---
# References
[[Error Correcting Codes]]