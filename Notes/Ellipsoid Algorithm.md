---
tags:
  - Note
  - Incomplete
---
202402091402

Tags : [[Combinatorial Optimisation]]
# Ellipsoid Algorithm
---
**Strong vs Weak polytime:**

An algorithm is said to be *strongly* polytime if
1. the number of arithmetic operations is polynomial in the number of integers/rational numbers present in the input, and
2. space used is polynomial in the size of the input.

> [!info] Integer $i$, $\log(|i|+1)=\langle i \rangle$ number of bits in the binary representation of $i$.
> Define $\langle x \rangle=\langle p \rangle+\langle q \rangle$ if $x= \frac{p}{q}$.

## Examples
---
1. Input $2^{n}$, i.e. $n$ bits, compute $2^{2^{n}}$.
Repeated squaring: $2\to {2}^{2}\to 2^{2^{2}}\to 2^{2^{3}}\to\dots$
$n$ arithmetic operations
But not polytime because exponential space is needed to write the output itself!

2. Euclid's GCD algorithm: Input $a,b$, input size $=\langle a \rangle+\langle b \rangle\approx \log a+\log b$
$a,b\to b\mod a,a\to\dots$ ($b>a$)
Each step reduces the number of bits by at least 1.
Number of arithmetic operations $\approx \log a+\log b$.
dependent on the size of the input numbers, hence weakly polytime

> [!question] Open: Is there a strongly polytime algorithm for LP?
## The algorithm
---
$\mathbb{B}^{n}:=\{ x \in\mathbb{R}^{n}\ |\ x^{T}x\leq 1 \}$, a unit ball of radius $1$ in $n$ dimensions.

**Ellipsoid:** $E=\{ Mx+s\ |\ x \in\mathbb{B}^{n} \}$, where $M$ is an $n\times n$ non-singular matrix, $s \in\mathbb{R}^{n}$, is the center of $E$.

> [!question] Why is it enough to find a feasible point while we wanted to find the optimal value, point?
> We can do a binary search to get the optimal point, provided the *region is reasonable* to binary search on.

$\min c^{T}x:Ax\geq b,x\geq 0$. Call this $P$.
$c^{T}x\leq c_{0},Ax\geq b$. This is feasible iff $Opt(P)\leq c_{0}$.
Perform a binary search on $c_{0}$.

At any vertex, $n$ tight constraints (linearly independent).
$A'x=b'$
$x=A'^{-1}b'= \frac{1}{\det(A')}Adj(A')b'$.

Largest integer in $A,b,c$ be $C$. (Assume integral $A,b,c$.) The determinant is at most $n!C^{n}$ (we can argue that it's at most $C^{n}$), then the size of any coordinate of any vertex would be $n\log n+n\log C$.

Making the ellipse look like an ellipse algebraically:
$E=\{ Mx+s\ |\ x \in\mathbb{B}^{n}$,
$y=Mx+s$
$x=M^{-1}(y-s)$

$$
\begin{align*}
E&=\{ y \in\mathbb{R}^{n}\ |\ M^{-1}(y-s)\in\mathbb{B}^{n} \}\\
&= \{ y \in\mathbb{R}^{n}\ |\ (y-s)^{T}M'^{-T}M^{-1}(y-s)\leq 1 \}\\
&= \{ y \in\mathbb{R}^{n}\ |\ (y-s)^{T}Q^{-1}(y-s)\leq 1 \}&&Q=MM^{T}\\
&= \left\{  y \in\mathbb{R}^{n}\ |\ \frac{y_{1}^{2}}{q_{11}}+\dots+\frac{y_{n}^{2}}{q_{nn}}\leq 1  \right\}.
\end{align*}
$$

$Q$ is positive definite.

*Goal:* Output a feasible point in the ellipsoid.
*Assumption:* The feasible region is either empty or has a volume $\geq\epsilon$.
*Observation:* Any vertex has rational coordinates; numerator and denominator $\leq(nC)^{n}$.
$L=$ sum of bits of all coefficients

**Algorithm:**
Initialise $E_{0}:$ ball of radius $4^{nL}$, $i=0$
while $vol(E_{i})\geq 2^{-(n+1)L}$
{
	If center $z_{i}$ of $E_{i}$ is feasible then output $z_{i}$, STOP
	Else $a_{k}^{T}x\leq b_{k}$ be (one of) the violated inequality
	$E_{i+1}=$ smallest ellipsoid containing $E_{i}\cap \{ x\ |\ a_{k}^{T}x\leq a_{k}^{T}z_{i} \}$
}
Output "infeasible", STOP

**Analysis:**
$E_{i}=$ unit ball
violated inequality: $x_{1}\leq 0$
$E_{i+1}=\left\{  x\ |\ \left( \frac{n+1}{n} \right)^{2}\left( x_{1}+\frac{1}{n+1} \right)^{2}+\left( \frac{n^{2}-1}{n^{2}} \right)\sum\limits_{i=2}^{n}x_{i}^{2}\leq 1  \right\}$
$$
\begin{align}
\dfrac{vol(E_{i+1})}{vol(E_{i})}&=\left(\dfrac{\left( \frac{n}{n+1} \right)\left( \sqrt{ \frac{n^{2}}{n^{2}-1} } \right)^{n-1}}{1} \right) \\
&=\left( 1- \frac{1}{n+1} \right)\left( 1+ \frac{1}{n^{2}-1} \right)^{(n-1)/2} \\
&\leq e^{ -\frac{1}{n+1}+\frac{1}{n^{2}-1}\frac{n-1}{2} }&&\dots1+x\leq e^{x} \\
&=e^{-\frac{1}{2n+2} } \\
&=f,
\end{align}
$$
which is the shrink in volume.

Number of iterations $\geq k$ if
$$
\begin{align}
f^{k}8^{n^{2}L}&\geq 2^{-(n+1)L} \\
k\log f+3n^{2}L&\geq-(n+1)L \\
k&\leq \frac{(n+1)L+3n^{2}L}{\frac{1}{2n+2}} \\
&=O(n^{3}L).
\end{align}
$$


### Minimum value assumption
---
$$Ax\leq b \xrightarrow{Perturb}Ax\leq b+\epsilon \vec{1}$$$$\text{feasible point }\hat{x}\mapsto \hat{x}\pm\epsilon \vec{1}\text{ as feasible points}$$
**Claim:** $Ax\leq b$ is feasible iff $Ax\leq b+\epsilon \vec{1}$ is feasible.
*Proof:* The forward direction is trivial.

For the backward direction, suppose the contrary.
By Farkas' lemma, $\exists y\geq 0$ s.t. $y^{T}A=0, y^{T}b=-1$
	LP: $\min y^{T}\vec{1}$ s.t.
	- $y^{T}A=0$
	- $y^{T}b=-1$
	- $y\geq 0$.
	Largest coefficient in absolute value $=C$.
	Each coordinate of $y$ is $\leq(nC)^{n}$.
$$
\begin{align}
y^{T}(b+\epsilon \vec{1})&=y^{T}b+\epsilon y^{T}\vec{1} \\
&\leq-1+\epsilon n(nC)^{n}.
\end{align}
$$

Choose $\epsilon= \dfrac{1}{2n(nC)^{n}}$.
$y^{T}(b+\epsilon \vec{1})\leq -\frac{1}{2}$

If $Ax\leq b+\epsilon \vec{1}$ is feasible, then let $\hat{x}$ be its solution.
$$
\begin{align}
A\hat{x} &\leq b+\epsilon \vec{1}\\
y^{T}A\hat{x} &\leq y^{T}(b+\epsilon \vec{1})\\
0&\leq-\frac{1}{2} \\
\implies&\impliedby
\end{align}
$$

last part aaaaaaaaaaaaaaaaaa



---
# References
