202301270201

Type : #Note
Tags : [[Category Theory]]

---
# Category Theory Introduction Page

```tikz 
\usepackage{tikz-cd} 
\begin{document} 
\begin{tikzcd}     T     \arrow[drr, bend left, "x"]     \arrow[ddr, bend right, "y"]     \arrow[dr, dotted, "{(x,y)}" description] & & \\
K & X \times_Z Y \arrow[r, "p"] \arrow[d, "q"]     & X \arrow[d, "f"] \\
& Y \arrow[r, "g"]     & Z 
\end{tikzcd}
\end{document} 
```


```tikz
\usepackage{tikz-cd}
\begin{document}
\begin{tikzcd}
& X\times Y \arrow[dl, "\pi_1"'] \arrow[dr, "\pi_2"]  & \\
X &  &  Y \\
& A \arrow[ul, "f"] \arrow[ur, "g"'] \arrow[uu, "\langle{f,g}\rangle", dashed]&
\end{tikzcd}
\end{document}
```








```tikz
\usepackage{tikz-cd}
\begin{document}
\begin{tikzcd}
X\cap Y 
\arrow[d, "j_2"'] 
\arrow[r, "j_1"]     
& 
X \arrow[d, "i_1"'] \arrow[rdd, "f", bend left] 
&   
\\
Y \arrow[r, "i_2"] \arrow[rrd, "g", bend right] 
&
X\sqcup_{X\cap Y}Y \arrow[rd, "!h", dashed]     
&
\\
&
& 
A
\end{tikzcd}
\end{document}
```



---
# References
Resources Used for making these notes:
- Books:
  - [An Invitation to Applied Category Theory: Seven Sketches in Composibilty](https://github.com/prathyvsh/category-theory-resources#an-invitation-to-applied-category-theory-seven-sketches-in-compositionality)
- Websites:
  - [A collection of resources on Github](https://github.com/prathyvsh/category-theory-resources)
