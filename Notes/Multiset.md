202306091706

Type : #Note
Tags : [[Enumerative Combinatorics]]

---
# Multiset

Intuitively a **Multiset** is a set with repeated elements, for example
$$
\{7,3,3,4,4,5\}
$$.
More precisely a **Finite Multiset**  $M$ on a set is a pair $(S,\nu)$ where $\nu:S\to \mathbb N$ such that $\sum\limits_{x\in S}\nu(x)$ is finite. Where $\nu(x)$ is the number of repetitions of $x$ and sum of all $\nu(x)$ is the cardinality of $M$.
if $S=\{x_{1}, x_{2}\dots x_{n}\}$ and $\nu(x_{i})=a_{i}$ then we can write $M=\{x_{1}^{a_{1}}, x_{2}^{a_{2}}\dots x_{n}^{a_{n}}\}$.
If $|M|=k$ then we say $M$ is a $k$-multiset.

The total number of multi-subsets of a multiset $M$ is
$$
\prod\limits_{x\in S} (\nu(x)+1)
$$
Analogous to the standard set we have a [[Multi-choose]] which denotes the number of sub-multisets of a set of order $k$ denoted as 
$$
\left(\!\!{n\choose k}\!\!\right)  
$$



---
# References
