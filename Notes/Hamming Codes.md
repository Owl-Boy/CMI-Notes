202308181608

Type : #Note
Tags : [[Algorithmic Coding Theory]]

---
# Hamming Codes
Given a message $(x_{1},x_{2},x_{3},x_{4})\in\{0,1\}^{4}$, Its corresponding Hamming code word(denoted by $C_{H}$) is
$$
C_{H}(x_{1},x_{2},x_{3},x_{4})=(x_{1},x_{2}.x_{3},x_{4},\ x_{2}\oplus x_{3}\oplus x_{4},\ x_{1}\oplus x_{2}\oplus x_{4},\ x_{3}\oplus x_{1}\oplus x_{4})
$$
and it is classified by the following parameters
$$
C_{H}:q=2,k=4,n=7,R=4/7
$$

```ad-note
title: Hamming Weight
Given any code $v$, its Hamming weight is the number of non zero entires in the code. It is denoted by $\text{wt}(v)$
```

The minimum Hamming weight is the minimum hamming distance between two codes.


---
# References
