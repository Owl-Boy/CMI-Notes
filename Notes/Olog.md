202304012304

Type : #Note
Tags : [[Category Theory]]

---
# Olog
**Ologs** or **Ontological Logs** is a graphical representation of sets of data and relations between them.
Example:
```tikz
\usepackage{tikz-cd}
\begin{document}
\begin{tikzcd}
    \fbox{\begin{tabular}{@{}c@{}}
        An amino acid\\
        found in dairy
    \end{tabular}} \arrow[rd, "is"']
    & 
    \framebox{argenine} \arrow[r, "has"] \arrow[l, "is"'] \arrow[d, "is"]
    & 
    \fbox{\begin{tabular}{@{}c@{}}
        an electrically-\\
        charged side\\ 
        chain
    \end{tabular}} \arrow[d, "is"]
    \\
    &
    \fbox{an amino acid} \arrow[r, "has"] \arrow[dl, "has"'] \arrow[dr, "has"]
    &
    \fbox{a side chain}
    \\
    \fbox{an amine group}
    &
    &
    \fbox{a carboxylic chain}
\end{tikzcd}
\end{document}
```

==TODO:== have to figure out how to put check marks or a symbol to show that the diagram commutes 

Normally Each arrow can be read by reading the label on its source box, then the label on the arrow, and finally the label on its target box, but sometimes a shorthand version will be used when obvious
for example:
```tikz
\usepackage{tikz-cd}
\begin{document}
\begin{tikzcd}
    &
    \fbox{\begin{tabular}{@{}c@{}}
        A pair $(x,y)$, where\\
        $x$ and $y$ are integers
    \end{tabular}} \arrow[rd, "y"] \arrow[ld, "x"']
    & 
    \\
	\fbox{an integer}
    &
    &
    \fbox{an integer}
\end{tikzcd}
\end{document}
```



---
# References
