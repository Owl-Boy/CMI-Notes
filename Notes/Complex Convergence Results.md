202301161101

Type : #Note
Tags : [[Complex Analysis]]

---
# Complex Convergence Results
### Series
```ad-note
title: 
A formal sum $\sum\limits_{n=0}^{\infty} a_n$;  $a_n \in \mathbb{C} \ \forall \ n$.
```
We say that a series is **convergent** if its sequence of partial sums is convergent.

### Geometric series
$\displaystyle \sum \limits_{n=1}^{\infty} z^n$ , $z \in \mathbb{C}$. 
The partial sums $S_n$ are given by $S_n = \dfrac{1-z^n}{1-z}$. 
The series converges iff $|z| < 1$, and limit $S = \dfrac{1}{1-z}$.

### Absolutely convergent
```ad-note
title: 
A sequence $\{a_n\}$ is called absolutely convergent if $\{|a_n|\}$ converges.

$\sum a_n$ is absolutely convergent if $\sum |a_n|$ is convergent.
```

#### Remarks:
1. Absolute convergence _does not_ imply convergence. For example, $|z_n| = 1 \ \forall \  n$ does not guarantee that $z_n$ will converge.
2. Convergence $\implies$ absolute convergence (for sequences).
3. Convergence _does not imply_ absolute convergence (for series). Example $a_j = (-1)^j/j$
4. Abs convergence $\implies$ convergence for series. (proof exercise)

### Cauchy sequence
```ad-note 
title: Theorem
A sequence $\{a_n\}$ is convergent iff given $\epsilon > 0, \exists \ N \in \mathbb{N}$ s.t. $|a_n-a_m| < \epsilon$ for all $m,n \ge N$.
```

### Pointwise convergence
```ad-note
title:
Let $F_n : E \to \mathbb{C}$, $n \in \mathbb{N}$, be a sequence of functions defined on $E\subset \mathbb{C}$.
$\{F_n\}$ is said to **pointwise converge** to a function $f:E \to \mathbb{C}$ if 
$$\lim\limits_{n\to \infty} f_n(z) = f(z) \ \forall \ z \in E$$
```

### Uniform convergence
```ad-note
title:
Let $F_n : E \to \mathbb{C}$, $n \in \mathbb{N}$, be a sequence of functions defined on $E\subset \mathbb{C}$.
$\{F_n\}$ is said to **uniformly converge** to a function $f:E \to \mathbb{C}$ if given $\epsilon > 0$, there exists $N \in \mathbb{N}$ such that $|f_m(z) - f(z)| < \epsilon \ \forall \ m \ge N\ \forall \ z \in E$. 
```
The limit function of a sequence of uniformly converging continuous functions is continuous.

#### Corollary:
Suppose $\{a_n\}$ is a convergent sequence s.t. $|f_n(z) - f_m(z)| \le |a_m-a_n|$ on $E$, then $\{f_n\}$ is uniformly convergent.

#### Corollary:
(Weierstrass M test)
Suppose $\sum f_n$  is a series of functions s.t. $|f_n(z)| \le M a_n$ for a sequence $\{a_n\}$, if $\{a_n\}$ converges then the series $\sum f_n$ converges.

---
# Related Problems

---
# References