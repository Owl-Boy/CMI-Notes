202210261010

Type : #Note
Tags : [[Algebra]]

---
# Composite Field

```ad-note
title: Composite Fields
If $K_1$ and $K_2$ are subfields of $K$, then the [[Composite Field| composite field]] of $K_1$ and $K_2$ denoted by $K_1K_2$, is the smallest subfield of $K$ which contains both $K_1$ and $K_2$. Similarly, the composite field of any collection of subfields of $K$ is the smallest subfield of $K$ which contains all the other ones.
```

If $K_1$ and $K_2$ are finite extensions of a field $F$, let $\alpha_1,\alpha_2\dots\alpha_n$ are and $F$-basis for $K_1$, let $\beta_1,\beta_2\dots\beta_m$ are and $F$-basis for $K_2$. The the composite field $K_1K_2$ over $F$ is:
$$
K_1K_2 = F(\alpha_1,\alpha_2\dots\alpha_n,\beta_1,\beta_2\dots\beta_m)
$$
_Proposition:_ $[K_1K_2:F] \le [K_1:F][K_2:F]$ with equality if and only the basis of one fields remains linearly independent over the other.
_Proof:_ $K_1K_2 = K_2(\beta_1,\beta_2\dots\beta_m)$ 
Hence $[K_1K_2:K_1] \le m = [K_2:F]$ 
Since $[K_1K_2:F] = [K_1K_2:K_1][K_1:F]$ 
hence proved
we also have the diagram.
$$
\begin{matrix}
& & K_1K_2 & & \\
\le m & \huge/ & & \huge \backslash & \le n \\
K_1 & & & & K_2\\
\ n & \huge\backslash & & \huge / & \le n \\
& & F & &
\end{matrix}
$$

---
# Related Problems

---
# References
