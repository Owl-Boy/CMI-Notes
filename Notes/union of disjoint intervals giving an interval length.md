---
tags:
  - Example
---

202408071236

tags :  [[Measure Theory]]

#  union of disjoint intervals giving an interval length
---
>[!question]
>Let $(a_1, b_1], (a_2, b_2] \dots$ be disjoint and $\bigcup (a_i, b_i) = (a, b]$, then show that $b-a = \sum b_i-a_i$

### Proof
The proof is in two parts:
#### $b -a \ge \sum b_i - a_i$
Consider any finite suffix of the series . Given the finite suffix, arrange the intervals in ascending order, so without loss of generality we have the following 

$$
a \leq a_{1} < b_{1} \leq a_{2} < b_{2} \leq \dots b_{n} \leq b
$$
and we get that 
$$
b - a = b - b - {b_{n}} + b_{n} - a_{n} \dots a_{1} - a
$$
hence forall $n\in \mathbb{N}$ we have $\sum_{i=1}^n (b_i - a_i) \le b-a$ .
This proof uses the fact that the real numbers are compact.
#### $b -a \le \sum b_i - a_i$
We prove this by extending the sub interval and shrinking the bigger interval. complete it later

---
# Related
