---
tags:
  - Note
  - Incomplete
---
202310191610

Tags : [[Algorithmic Coding Theory]]

---
# Lifted Reed Solomon Codes

```ad-hint
title: Motivation
Using RM codes we can have constant distance and $n^{\beta}$ query complexity codes, but the rate has to be less than $1/2$, once $m>1$. We would like to achieve higher rates because that would mean less redundancy. Hence, lifted RS codes.
```

$\{f:\mathbb{F}_{q}^{n}\to \mathbb{F}_{q}\ |\ \text{For every line }L=\{ \vec{a}+\vec{b}t \}, f|_{L}\text{ agrees with a poly of degree at most }d\}$

Any codeword $f$ of RM ($m,d,\mathbb{F}_{q}$) code is also a codeword of lifted RS. But it is not immediate why there are more codewords in lifted RS.

$m=2$, $\mathbb{F}_{q}$ of characteristic $2$
Which functions $f:\mathbb{F}_{q}^{2}\to \mathbb{F}_{q}$ lie in the lifted RS code?


---
# References
[[Reed-Solomon Codes]]
