---
tags:
  - Example
---

202409302056

tags : [[Probability]]

#  Kolmogorov's Law of Large Numbers
---
>[!Theorem] Kolmogorov's Strong law of Large Numbers
>1. Let $(X_{n})$ be a series of independent mean 0 random variables such the series of numbers $\sum \frac{1}{2} \text{var}(X_{n})$ converges, then $\frac{1}{n}\sum X_{n}\to{0}$
>2. In particular, for a sequence of independent identically distributed random variables with finite mean and variance, their average converges to the mean almost surely.

From Kolmogorov's theorem, we know that $\sum \frac{X_{n}}{n}$ converges almost surely.

To prove that 
$$
\sum \frac{x_{i}}{i} \to c \implies \frac{1}{n}\sum x_{i} \to 0
$$
Then we are done.
let $s_{m} = \sum_{i=1}^n \frac{x_{i}}{i}$ then we can write $x_{i} = m(s_{m} -s_{m-1})$
Then using Cesaro's theorem, we get the answer trivially.

---
# Related
