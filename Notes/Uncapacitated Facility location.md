---
tags:
  - Note
---
202309211309

Tags : [[Advanced Algorithms]]

---
# Uncapacitated Facility location (no max number of customers for each facility)

Set of $n$ possible locations for opening facilities.
- Cost $f_i \geq 0$ for opening a facility at $i^{th}$ location
- Set of customers ($m$) that need to be connected to an open facility. Multiple customers can connect to one facility.
- Cost $c_{ij} \geq 0$ for connecting customer $j$ to facility $i$.

**Goal:** Choose a set of facilities to open s.t. total cost (opening + connections) is minimum.

---
## LP
Minimise $\sum\limits_{i} f_{i}x_{i} + \sum\limits_{i,j} c_{ij}y_{ij}$ s.t.:
- $\sum\limits_{i} y_{ij} \geq 1$ $\forall j$
- $x_i \geq y_{ij}$ $\forall i,j$
- $x_i, y_{ij} \in [0,1]$ $\forall i,j$.

```ad-info
There is a simple reduction from set cover to facility location. So this problem has no constant factor approximation either.
So we'll assume metric property: $c_{i',j'} \leq c_{ij'} +c_{i'j} +c_{ij}$. (since no triangles)
```

Solve LP. Let LP OPT be $x^*, y^*$.

We can't simply round up every non integer to $1$ because we might end up opening a lot of facilities which would be very expensive and unnecessary. Hence we will do rounding in two stages.
Two stages of rounding:
1. $x^*,y^* \to x',y'$ (not integral solution)
2. $x',y' \to$ integral solution

LP OPT value $= \sum\limits_{i} f_{i}x^{*}_{i} + \sum\limits_{i,j}c_{ij}y_{ij}^*$
Connection cost in LP OPT for customer $j = \sum\limits_i c_{ij} y_{ij}^* = c^*_j$

In LP OPT $\sum_i y_{ij}^* = 1$ $\forall j$ and $y^*_{ij} = Pr[\text{connecting } j \text{ to } i]$ 

We will set all the connections that take more than $2c^*_j$ to $0$, because they are 'too expensive'. (Here $2$ is chosen arbitrarily, we can do the same thing with some constant $\alpha$.)

---
#### Rounding I
$\forall j$ $S_j = \{ i | c_{ij} \leq 2c^*_j\}$
$y'_{ij} = 0$ if $i \notin S_j$

We can't simply set the non zero values in $S_j$ to themselves because we'll violate the constraint that their sum should be $\geq 1$.
So we scale all of them to make the sum equal to $1$.

$y'_{ij} = \dfrac{y^*_{ij}}{\sum_{i \in S_j} y^*_{ij}}$  $\forall i \in S_j$.

```ad-info
title:
**Lemma 1:** $\sum\limits_{i \in S_j} y^*_{ij} \geq 1/2.$
($\implies y'_{ij} \leq 2y^*_{ij}$.)
*Proof:*
$$
\begin{align*}
c_j^* &= \sum_i c_{ij} y^*_{ij}\\
&\geq \sum_{i \notin S_j} c_{ij} y^*_{ij}\\
&> \sum_{i \notin S_j} 2c^*_j y^*_{ij}\\
c^*_j &> 2c^*_j \sum_{i \notin S_j} y^*_{ij}\\
\sum_{i \notin S_j} y^*_{ij} &< \frac{1}{2}.\\
\end{align*}
$$
```

$y'_{ij} \geq y^*_{ij}$ $\forall i \in S_j$
$x'_i \geq y'_{ij}$
$x^*_i \geq y^*_{ij} \geq \frac12 y'_{ij}$
We can safely round up $x^*_i$ by a factor of $2$ to satisfy the second constraint that $x_i \geq y_i$.

Set $x'_i = \min\{2x^*_i, 1\}$
*Observe:* $x', y'$ is a feasible solution of LP.

cost $(x', y') \leq 2$.cost $(x^*, y^*)$

---
#### Rounding II

1. Pick a customer $j$ st $c_j^*$ is minimum.
2. Pick $i \in S_j$ with minimum $f_i$. Open $i$. Connect $j$ to $i$.
3. For every (unassigned) customer $j'$ st $S_j \cap S_{j'} \neq \phi$. Connect $j'$ to $i$.
Repeat until all customers are assigned to a facility.

Let $L$ be the set of facilities opened
Let $C_f(L) =$ opening cost of $L$
	$C_r(L) =$ connection cost of $L$.

##### Lemma 2:
1. $C_f(L) \leq 2\sum_i f_i x^*_i$
2. $C_r(L) \leq 6 \sum_{ij} c_{ij}y^*_{ij}$ 
$\implies$ cost$(L) \leq 6 LP.OPT$.

*Observe:* If $j_1$ and $j_2$ are picked in Step 1 of the algorithm then $S_{j_1} \cap S_{j_2} = \phi$.




---
# References
[[Linear Programming]]