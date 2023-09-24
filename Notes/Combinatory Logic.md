---
tags:
  - Note
  - Incomplete
---
202309210909

Tags : [[Logic]], [[Lambda Calculus]]

---
# Combinatory Logic
## Syntax
$$
\begin{matrix}M,N & := & x & | & S & | & K & | & MN\end{matrix}
$$
such that 
$$
\begin{align*}
K\ M\ N &\to_{\omega} M\\
S\ M\ N\ P &\to_{\omega} M\ P\ (N\ P)
\end{align*}
$$
We can also build 
- $I$ as $SKK$
- $B = S(KS)K$
- $W = SS(KI)$

[[Lambda Term In Combinatory Logic]]


---
# References
