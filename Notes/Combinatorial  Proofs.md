202305281305

Type : #Note
Tags : [[Enumerative Combinatorics]]

---
# Combinatorial  Proofs
A proof that is done by creating a bijection from a set of a set of known size. These kinds of proof can be extremely elegant and easy to understand and one of my favorite ways to prove an identity.

The precise border between **Combinatorial Proofs** and **Non-Combinatorial Proofs** is hazy, because A more formal looking proof might have combinatorial ideas behind it which might not be noticed by someone who is aware of standard techniques of converting apparently Non Combinatorial arguements to Combinatorial ones. In such a case a more knowledgeable mathematician would find the argument combinatorial while a novice would not.

---

# Example
Let $n$ and $k$ be positive integers. How many ways are there to pick $k$ subsets of $[n]$ $(X_{1},X_{2}\dots X_{k})$ such that $X_{1}\cap X_{2}\dots X_{k}=\emptyset$ 

The Following is a non combinatorial proof.
Say $\bigcap\limits_{i=1}^{k-1} X_i=T$  
let $Y_{j}= X_{j}\setminus T$ hence $\bigcap Y_j=\emptyset$
Hence there are $f(k-1,n-1)$ such collectoins for $X_i$ and $X_k$ can be any subset of $[n]\setminus T$ . if $\#T=m$, then there are $n\choose m$ possible $T's$, thus we get
$$
\begin{align*}
f(k,n) &= \sum\limits_{i=0}^{n} {n\choose i} 2^{n-i}f(k-1,n-i)
\end{align*}
$$
Let $F_k(x)=\sum\limits_{n\ge0}f(k,n) \frac {x^{n}}{n!}$ . Then from the above equation we get
$$
F_{k}(x)= e^{x}F_{k-1}(2x)
$$
where $F_{1}(x)=e^{x}$ so we get that
$$
\begin{align*}
F_{k}(x)&= exp(x+2x+4x+\dots+2^{k-1}x)\\
&= exp(2^{k}x-x)\\
&= \sum\limits_{n\ge0}(2^{k}-1)^{n}\frac{x^{n}}{n!}
\end{align*}
$$
So $f(k,n)=(2^{k}-1)^{n}$

The previous proof is rather long and non elegant, and solution is surprisingly simple. $(2^{k}-1)^{n}$ also happens to be the number of $n$ tuples of stict subsets of $[k]$.
The easy to understand bijection between the two sets gives a very elegant combinatorial proof.

Given an element of $(Z_{1},Z_{2},\dots, Z_{n})$ which are all strict subsets of $[k]$ we say that an element $i\in X_{j}\iff j\in Z_{i}$. Which means that the set $Z_{i}$ denotes all of the $k$ sets that contain $i$, which are not all sets, which confirms that the intersection of all $X_{i}$ will be empty.
The exact proof is to show two trival injections between the sets of tuples.

---
# References
[[How to count]]
