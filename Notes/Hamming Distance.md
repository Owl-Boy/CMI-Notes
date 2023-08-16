202308101608

Type : #Note
Tags : [[Algorithmic Coding Theory]]

---
# Hamming Distance
Given two vectors $\vec u, \vec v$ the hamming distance $\Delta(\vec u, \vec v)$ is the number of positions at which they differ

an $n-$symbol $t-$error channel over $\Sigma$ is a function $ch:\Sigma^{n}\to\Sigma^{n}$ such that  ^88a6ce
$$
\forall \vec v\in\Sigma^{n},\ \Delta(\vec v, ch(\vec v))\le t
$$
It can be thought of as a channel that takes in $n-$length words and can make up to $t$ error for an input word


**Hamming Distance is a Distance**

---
# References
[[Error Correcting Codes]]
[[Hamming Bound]]