202305281205

Type : #Note 
Tags : [[Enumerative Combinatorics]]

---
# Generating Functions
**Generating Function** is the most useful but most difficult to understand methods for evaluting $f(x)$.
The two most common types of **Generating Functions** are called [[Ordinary Generating Functions]] and [[Exponential Generating Functions]].

Generating Function is called a former series because the actual values of $x$ is not relevant, and neither do we care about the covergence of the series. The term $x^n$ is merely a marker for $f(n)$. 

Generating Functions are useful because we can apply ==various operations that have combinatorial significance==, for example we can add two generating functions, or multiply generating functions. There operations are what we would get by treating generating functions as standard algebraic objects and properties of algebraic structures that arise for example $\mathbb C[[x]]$ can be helpful in analysis of the functions.

--- 

# Example
Find a simple expression for the generating function $F(x)=\sum\limits_{n\ge0}a_{n}x^{n}$ where $a_{0}=a_{1}=1$ and $a_n=a_{n-1}+a_{n-2}$ for $n\ge 2$ 
We have 
$$
\begin{align*}
F(x)=\sum\limits_{n\ge0} a_{n}x^{n} &= 1 + x + \sum\limits_{n\ge2} a_{n}x^{n}\\
&= 1+x+\sum\limits_{n\ge2}(a_{n-1}+a_{n-2})x^n\\
&= 1+x+x^{2}\sum\limits_{n\ge0}a_{n}x^{n}+x\sum\limits_{n\ge0}a_{n}x^{n}\\
F(x) &= 1 + x + xF(x) + x^{2}F(x)\\
F(x)&= \frac{1}{1-x-x^{2}}
\end{align*}
$$

---
# References
