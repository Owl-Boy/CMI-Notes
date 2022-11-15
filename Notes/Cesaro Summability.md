2022-11-13 03:11 pm

Type : #Note
Tags : [[Analysis]]

---
# Cesaro Summability

```ad-note 
title:Motivation 
Sometimes convergence of a series is too much to ask for, so you look at convergence of an average series.

Given a series $\sum c_n$, let $s_n$ be the partial sums of the series. Then,
$$\sigma_N \colon= \dfrac{s_0 + s_1 + \cdots s_{N-1}}{N}$$
$\sigma_N$ is called the $N$th Cesaro mean of the sequence $\{s_n\}$ or the $N$th Cesaro sum of the series $\sum c_n$.

If $\sigma_N$ converges to $\sigma$ as $N$ tends to infinity, then the series $\sum s_n$ is said to be *Cesaro summable* to $\sigma$.

For example the sequence, $0,1,0,1,\cdots$ is not convergent.
But it's cesaro sums converge to $1/2$. 
```

- Cesaro sums of a convergent series converge to the series limit.
  ### Proof:
  Let $\displaystyle\sum\limits_{k=0}^{\infty} c_k = c$.
  Let $\sigma_N = \dfrac{s_0 + s_1 + \cdots s_{N-1}}{N}$
  Look at $|c-\sigma_N| = \left|\dfrac{(c-s_0)+(c-s_1)+\cdots(c-s_{N-1})}{N}\right|$.
  $\implies |c-\sigma_N| \le \dfrac{|c-s_0| + \cdots |c-s_M|}{N} + \dfrac{|c-s_{M+1}|+\cdots+|c-s_{N-1}|}{N}$
  where $m$ is such that $|s_k-c| < \epsilon$ for all $k > m$.
  $\implies |c-\sigma_N| \le (N-M-1)\epsilon/N + F/N \le 2\epsilon$
  for large N.

---
- 

---
# Related Problems
[[Fejer Kernel]]

---
# References
[[Fourier Series]]

