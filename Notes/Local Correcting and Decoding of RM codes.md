---
tags:
  - Note
  - Incomplete
---
202310171610

Tags : [[Algorithmic Coding Theory]]

---
# Local Correcting and Decoding of RM codes
```ad-hint
title: Motivation
We know that we can get a univariate polynomial back from its evaluations on some points that are equally spaced apart by taking consecutive differences, which will be a lower degree polynomial, the differences of which will be a polynomial with degree yet lower and so on.
So if we want to correct the evaluation of a polynomial at $(\vec{a})$, then we can pick a random direction $(\vec{b})$ and look at the evaluations on the line $L=\{\vec{a}+\vec{b}t\}$ and 
```

**Theorem:** $RM_{2}(m,1)$ is $(\delta,2,1-2\delta)$-LCC for any $\delta< \frac{1}{q}$.
*Proof:*



---
**Ideas for self-correction**
- Basic decoding using interpolation on lines $(d+1,\delta,(d+1)\delta)$-locally correctable
- Improved decoding using Reed Solomon decoding on lines $\left( q-1,\delta, \frac{2\delta}{1-\sigma} \right)$ where $0<\sigma<1,d\leq\sigma(q-1)-1$.
- Decoding on curves

---
### Basic decoding
Shoot a random line through $\vec{w}$. $L=\{ \vec{w}+\lambda  \vec{v} \ |\ \lambda \in\mathbb{F^{*}_{q}} \}$
Each individual query of the corrector samples a uniformly random location. With probability at least $1-(d+1)\delta$ it never queries a corrupted coordinate.



---
# References
[[Reed-Muller Codes]]
[[Local Decoding]]