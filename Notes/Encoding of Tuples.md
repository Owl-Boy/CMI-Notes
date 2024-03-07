---
tags:
  - Note
  - Incomplete
---
202403080103

Tags : [[Logic]]
# Encoding of Tuples
---
Now that we have defined an encoding for *CNF* formulas, it would be nice to have some **infrastructure** that would let us build such formulas, to do so, we define  the following tuple $(\gamma, V_{1}, V_{2}\dots V_{t})$ where $V_{1}\dots V_{t}$ are a partition of $[1\dots n-1]$.

This can be encoded as
```
mu_h(gamma, v1...vt)=mu_h(gamma)<asn>
                                     <val>mu_h(0)V(0)</val>
                                     .
                                     .
                                     .
                                     <val>mu_h(n-1)V(n-1)</val>
                                </asn>
```
Where `V(n)` is $k$ such that $n\in V_k$.

This also lets us have an encoding before assignments, which would just be like assigning the same thing to all the numbers.

---
# References
[[Encoding for Proposition Formulas]]
[[Succinct Encoding of Natural Numbers Using Strings]]