---
tags:
  - Note
---
202403071503

Tags : [[Logic]]
# Succinct Encoding of Natural Numbers Using Strings
---
Obviously, given an alphabet $\Sigma$ such that $|\Sigma| = m$, for any number $n$ we can find a numeral of size roughly $\log_m{n}$. Which is the optimal encoding for the size of the string. But we want to work with natural numbers using first order logic, so another possible goal would be to find an encoding of natural numbers to optimise the size of the [[First Order Logic|FOL]] formula that distinguishes them.

>[!tldr] Goal
>The following is a sequence of encodings such that for every $h\geq 0$, there is an encoding such that  for every $n\geq 0$ there an a first order formula of length $O(n)$ stating that two words encode the same numbers smaller than $T(h, n)$.

For each $h\ge 1$ we define $\Sigma_{h} =\{ \text{0,1,<1>,</1>}\dots \text{<h>,</h>}\}$ Which we use to define the encoding.

- $\mu_{1}(0)= \text{<1></1>}$
- $\mu_{1}=\text{<1>bit}(0,n-1)\text{bit}(1,n-1)\dots \text{bit}(L(n)-1,n-1)\text{</1>}$
	- Can also be thought of as the binary representation of $n-1$ between tags
- ![[Pasted image 20240307154605.png]]
>[!example]
>$\mu_2(50)$ can be written as
>```
><2>
>    <1></1>1
>    <1>0</1>0
>    <1>1</1>0
>    <1>01</1>0
>    <1>11</1>1
>    <1>001</1>1
></2>
>```

We show that the encoding has the desired property [[Lemma for Natural Number Encoding|here]].

--- 
## Size of the Encoding
>[!Theorem] 
>Given an $n$ and an $h$, the size of the encoding is $|\mu_{h}(n)|\in O(h \cdot (\lg n)^2)$. Which is also an upper bound for computing the size.

We define $P_m(n)=\prod_{i\leq m} L^i(n)$, and by a straightforward induction we have 
$$
|\mu_{h}(n)| \leq 4\cdot P_{h}(n)
$$
![[Pasted image 20240307173301.png]]
We also trivially have $(\lg^2(n))^2 < \lg(n)$.
Now we will show that $P_h(n)\leq c\cdot (L(n))^2$ for some $c$. This can also be done by a straightforward induction.
 ![[Pasted image 20240307173325.png]]

For the second part of the theorem we get a function for the running time recursively as define below
$$
R(h, n) = O(L(n)) + \sum_{i=0}^{L(n)}R(h-1, L(i))
$$
This is very similar to the first recurrence relation and can be proved with a similar method.

---
# References
[[First Order Logic]]
[[Revisiting Complexity of First-Order and Monadic-Second-Order Logic]] (notation)
[[Lemma for Natural Number Encoding]]