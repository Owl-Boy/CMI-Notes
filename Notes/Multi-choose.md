202306091706

Type : #Note
Tags : [[Enumerative Combinatorics]]

---
# Multi-choose
A **Multi-choose** is the [[Multiset]] version of combination "choose" for simple sets. It is denoted as
$$
\left(\!\!{n\choose k}\!\!\right)
$$
Which denotes the number of $k$ order multi-subsets of a set of order $n$. Or the number of was of choose $k$, not necessarily distinct objects from a set of $n$ elements.

```ad-note
title: Proposition
$$
\left(\!\!{n\choose k}\!\!\right)={n+k-1\choose k}
$$
```
One combinatorial proof with its explanation is the following.
**Proof:**
We create a set $Y = \{y_{1}, y_{2},\dots\}$ which represents the multiset $M$ and let the underlying set $S=\{x_{1},x_{2},\dots,x_{n}\}$.
Then we start creating a function $f:Y\to S$ and that function defines the sub-multiset in the following way.
$f$ will be a surjection and elements mapping to the same element in $S$ will represent copies of that element in $M$.
We start by mapping $y_{1}\mapsto x_{1}$ then $y_{2}\mapsto x_{2}$ until we find the first element $x_{i}$ that is in our multiset, to denote that, say $y_{j}\mapsto x_{i}$ and $x_{i}\in M$ then we say $y_{i+1}\mapsto x_{i}$. since for each element of the sub-multiset we are adding atmost 1 extra element to $Y$, the size of why should be $n+k$ and to identify a function, we assume the procedure used to for the set and mark each elment that represents one in the multiset. they can be any $k$ except for the last one hence the total number being $n+k-1\choose k$. This is a bijection as different functions would give different sub-mulitsets, which will differ atleast at the first place where the functions will disagree. The following is a diagramatic description of the procedure.



---
# References
