202304020404

Type : #Note
Tags : [[Category Theory]]

---
# Coproducts in Category Theory

The [[Universal Property]] for Products in Category Theory  is 

Let $X$ and $Y$ be sets, then for any set $A$ and functions $f:X\to A$ and $g:Y\to A$, there exists a unique function $h:X\sqcup Y\to A$ such that the following diagram commutes.
```tikz
\usepackage{tikz-cd}
\begin{document}
\begin{tikzcd}[column sep=small]
& 
X\sqcup Y 
\arrow[dd, "h", dashed] 
& 
\\
X 
\arrow[ur, "i_1"] 
&  
&
Y 
\arrow[ul, "i_2"']  
\\
& 
A \arrow[ul, "f"] \arrow[ur, "g"']
&
\end{tikzcd}
\end{document}
```
where 
$$
\begin{equation}
h(a)=
\begin{cases}
f(a)&a\in X\\
g(a) & a\in Y 
\end{cases}
\end{equation}
$$
and $h:X\sqcup Y\to A$
Since this is a universal property, Any object $B$ such that given two functions from a set $X$ to $A$ and $Y$ to $A$ gives a unique map from $B$ to $A$ then $B$ is isomorphic to $X\sqcup Y$.


---
# References
[[Product topology]]
