---
tags:
  - Note
  - Incomplete
---
202309211509

Tags : [[Algorithmic Coding Theory]]

---
# Guruswami-Sudan's list decoding of RS codes

| Fraction of errors           | Decodability                  |
| ---------------------------- | ----------------------------- |
| $(0,\frac{1-R}{2})$          | unique decoding               |
| $(\frac{1-R}{2},1-\sqrt{R})$ | list decoding (poly big list) |
| $(1-\sqrt{R},1-R)$           | *no clue*                     |
| ($1-R,1$)                    | exponentially many codewords                              |

---
## Sudan's algorithm
### 1. Interpolation step
Find a low-degree polynomial $Q(X,Y)$ s.t. $Q(\alpha_{i},y_{i})=0$ $\forall i = 1, \dots ,n$

### 2. Root finding step
Factor $Q(X,Y)$ to find polynomials $f(X)$ s.t. $Q(X,f(X)) = 0$.
Return all such $f$.

(We need some conditions to do 1. and 2.)*



---
# References
[[Reed-Solomon Codes]]
Mary Wootter's notes