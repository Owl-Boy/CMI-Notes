---
tags:
  - Note
---
202309210909

Tags : [[Logic]], [[Lambda Calculus]]

---
# Combinatory Logic

```ad-cite
title:History
This section ties more stuff in *Logic* and *Lambda Calculus*
Namely representing [[Hilbert Style Proofs]] with **Combinators**.
And the emulation of *Lambda Calculus* with **Combinators** directly translates to Deduction Theorem for *Hilbert's Proof System*
```

## Syntax
The **Context Free Grammar** for _Combinatory Logic_
$$
\begin{matrix}T & := & x & | & S & | & K & | & T\ T\end{matrix}
$$
such that 
$$
\begin{align*}
K\ M\ N &\to_{\omega} M\\
S\ M\ N\ P &\to_{\omega} M\ P\ (N\ P)
\end{align*}
$$
and $x$ is a variable, while $T\ T$ represents application.


We can also build 
- $I$ as $SKK$
- $B = S(KS)K$
- $W = SS(KI)$

*Combinators* can also be defined as all [[Lambda Calculus Syntax|Closed Lambda Terms]]. 

[[Lambda Term In Combinatory Logic]]


---
# References
