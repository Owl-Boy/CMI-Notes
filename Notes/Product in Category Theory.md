202304020304

Type : #Note
Tags : [[Category Theory]]

---
# Product in Category Theory
The [[Universal Property]] for Products in Category Theory  is 

Let $X$ and $Y$ be sets, then for any set $A$ and functions $f:A\to X$ and $g:A\to Y$, there exists a unique function $A\to X\times Y$ such that the following diagram commutes.
```tikz
\usepackage{tikz-cd}
\begin{document}
\begin{tikzcd}[column sep=small]
& 
X\times Y \arrow[dl, "\pi_1"'] \arrow[dr, "\pi_2"]  
& 
\\
X 
&  
&
Y 
\\
& 
A \arrow[ul, "f"] \arrow[ur, "g"'] \arrow[uu, "\langle{f,g}\rangle", dashed]
&
\end{tikzcd}
\end{document}
```

Since this is a universal property, Any object $B$ such that given two functions from a set $A$ to $X$ and $Y$ gives a unique map to $B$ and $B$ is isomorphic to $X\times Y$.

### Ologging Products
Given two objects $c,d$ in an [[Olog|olog]], there is a canonical label $\langle\langle c\times d \rangle\rangle$ for their product, which can be understood as:=
	A pair $(x, y)$, where $x$ is $\langle\langle c\rangle\rangle$ and $y$ is $\langle\langle d\rangle\rangle$ 
The projections can be labelled as "yields, as $x$" and "yields, as $y$" respectively

```tikz
\usepackage{tikz-cd}
\begin{document}
\begin{tikzcd}[column sep=large, row sep=large]
	\fbox{a car owner}
    \arrow[rr, "{\begin{tabular}{@{}c@{}}
	    yields, insofar\\
	    as it is a person\\
	    and owns, as\\
	    primary, a car
    \end{tabular}}"]
    \arrow[dd, "is"]
    \arrow[rrdd, "{\begin{tabular}{@{}c@{}}
	    owns, as\\
	    primary
    \end{tabular}}", near start, crossing over]
	&&
    \fbox{\begin{tabular}{@{}c@{}}
        a pair $(x,y)$,\\
        where $x$ is a\\
        person and $y$ is\\
        a car
    \end{tabular}} 
    \arrow[rr, "\begin{tabular}{@{}c@{}}
	    has as associ-\\
	    ated utility
    \end{tabular}"]
    \arrow[dd, "{yields,\ as\ y}"]
    \arrow[ddll, "{yields,\ as\ x}", near end]
    &&
    \fbox{a dollar value}
    \\\\
    \fbox{a person}
    &&
    \fbox{a car}
\end{tikzcd}
\end{document}
```

---
# References
[[Coproducts in Category Theory]]
